# Codespace

Aqui, as coisas são mais difíceis de entender, mas vou tentar resumir de forma objetiva. Caso queira entender todos os detalhes, basta acessar [aqui](https://github.com/vistomia/testando-update) para entender o que cada linha faz.

Abra o arquivo da pasta `.devcontainer/devcontainer.json`
Adicione isso ao objeto

```json
  "postAttachCommand": {
        "tko": "set +x && ps aux | grep '[b]ash' | grep -v $$ | awk '{print $2}' | xargs kill -9; clear && bash .devcontainer/attach.sh",
        "tk0": "sleep 1 && set +x && ps aux | grep '[b]ash' | grep -v $$ | awk '{print $2}' | xargs kill -9 && clear && bash .devcontainer/attach.sh"
  }
```

Crie o arquivo `attach.sh` na pasta `.devcontainer`. E coloque esse script dentro dele.

```sh
set +x 
pipx upgrade tko && clear
echo -e \033[1;32mTudo pronto para mais uma jornada! 😊\033[0m
tko -v
echo ""
echo ""
read -p "Pressione Enter para continuar..." # espera úsuario apertar Enter

if [ -d poo ]; then
    tko play poo
else
    echo s | tko init --remote poo # confirma a instalação do diretorio ./poo
    echo ts | tko play poo         # configura a versão para ts e abre
fi
```

Faça um push do repositório para salvar as alterações.

```sh
git add .
git commit -m "teste vitin"
git push
```

E reconstrua o container do Codespace.

![Image Gif](codespace-rebuild-container.gif)