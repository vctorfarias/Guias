## Ubuntu

Você pode criar um `alias`, que é uma maneira de criar atalhos personalizados para comandos no terminal. Isso permite substituir o comandos como `pipx upgrade tko && tko play poo` por nomes mais simples. Nesse caso vou usar o `play` mas você pode escolher qualquer outro.
```sh
echo "alias play='pipx upgrade tko && tko play poo'" >> ~/.bashrc
```
*obs.: a execução não vai retornar nenhum aviso de sucesso.*

Agora, sempre que você digitar `play` no terminal, ele executará o comando para atualizar o `tko` e iniciá-lo.
