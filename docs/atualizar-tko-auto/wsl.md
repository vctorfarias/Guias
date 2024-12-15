# WSL

Você tem duas opções:

1. Sempre que digitar `play`, em um terminal do `wsl`, ele irá atualizar o tko e iniciá-lo.
2. Sempre que abrir um terminal do `wsl` ele irá abrir o tko.

## Opção 1

Você pode criar um `alias`, que é uma maneira de criar atalhos personalizados para comandos no terminal. Isso permite substituir o comandos como `pipx upgrade tko && tko play poo` por nomes mais simples. Nesse caso vou usar o `play` mas você pode escolher qualquer outro.

```sh
echo "alias play='pipx upgrade tko && tko play poo'" >> ~/.bashrc
```
*obs.: a execução não vai retornar nenhum aviso de sucesso, mas tá tudo bem 👍*

Agora, sempre que você digitar `play` no terminal, ele executará o comando para atualizar o `tko` e iniciá-lo. Caso precise realizar alguma mudança. Leia a **Opção 2** e edite o `~/.bashrc`, pois o `alias` que você criou fica salvo nele.

## Opção 2

#### Sobre o Nano e o `.bashrc`

O Nano é um editor de texto, que roda no terminal. Ele é ideal para editar arquivos de configuração, como o `.bashrc`. 

O `.bashrc` é um arquivo de configuração do Bash (o terminal padrão na maioria das distribuições Linux). Ele é executado sempre que você abre um novo terminal interativo e serve para personalizar o ambiente de trabalho, como adicionar aliases, variáveis de ambiente e customizações.

#### Siga o passo a passo

- Abra o **WSL**
```
wsl ## ou abra pelo o programa Ubuntu
```
- Abrindo o Nano e Editando o `.bashrc`
```sh
sudo nano ~/.bashrc
```
Aperte as teclas
```
Ctrl + W # Abri o menu de pesquisa
Ctrl + V # Desce para a última linha
```

Digite no arquivo os comandos que deseja realizar sempre que abrir o terminal do `wsl`. Exemplo:

```sh
## Atualizar tko
pipx upgrade tko

## Caso queira iniciar o tko junto com o wsl
cd nome-da-pasta-do-meu-repositorio
tko play poo
```
Aperte as teclas
```
Ctrl + O ## Salva
Enter    ## Confirma
Ctrl + X ## Fecha o Nano
```
