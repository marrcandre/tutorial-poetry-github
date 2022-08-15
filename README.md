# Tutorial - Poetry e GitHub

Tutorial para uso de ambiente virtual Python com poetry e uso de git com GitHub.

# Aula 1 - Preparação do ambiente virtual

## Preparação do ambiente

**Escolha um local**

-   Abra o navegador de arquivos
-   Escolha um local no seu computador (p.e., Downloads, Documentos, etc.)
-   Crie uma pasta para o seu projeto
-   Certifique-se de que **nenhuma pasta** no caminho tenha **espaços** ou **acentos** (_se você não fizer isso, terá que recriar todo o projeto_).
-   Abra a **pasta** no vscode (repita em voz alta: _"Nunca abra um arquivo, sempre abra a pasta."_).
-   A pasta pode ser aberta pelo navegador de arquivos, botão direito do mouse, e "Abrir pasta com Visual Studio Code".
-   A pasta também pode ser aberta pelo terminal, de dentro da pasta, com o seguinte comando: `code .`
-   Dentro do vscode, abra um terminal (`Control+Shift+´`)

**Criando o ambiente virtual com o poetry**

Os comandos a seguir serão digitados no terminal que você abriu dentro do **vscode**.

Verifique se o **poetry** está instalado:

    poetry --version

Verifique se o **python** está instalado:

    python --version
    python3 --version

Verifique as configurações do **poetry**:

    poetry config --list

Informe ao **poetry** para criar a pasta do ambiente virtual dentro da pasta do projeto:

    poetry config virtualenvs.in-project true

**Criação do ambiente virtual**

Crie o ambiente virtual usado o **poetry**:

    poetry init

Você passará por uma tela semelhante a essa:

```bash
This command will guide you through creating your pyproject.toml config.

Package name [projeto]:
Version [0.1.0]:
Description []:
Author [Marco André Mendes <marcoandre@gmail.com>, n to skip]:
License []:
Compatible Python versions [^3.10]:

Would you like to define your main dependencies interactively? (yes/no) [yes] no
Would you like to define your development dependencies interactively? (yes/no) [yes] no
Generated file

[tool.poetry]
name = "projeto"
version = "0.1.0"
description = ""
authors = ["Marco André Mendes <marcoandre@gmail.com>"]

[tool.poetry.dependencies]
python = "^3.10"

[tool.poetry.dev-dependencies]

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"


Do you confirm generation? (yes/no) [yes] yes
```

Ative o ambiente virtual recèm criado:

    poetry shell

Para verificar o tamanho da pasta do ambiente virtual:

    du -sh .venv

**Instalação de pacotes**

Para instalar pacotes no nosso ambiente virtual, utilizamos o comando a seguir

    poetry add <pacote>

**Configurando o interpretador Python**

-   Ao abrir um arquivo `.py`, verifique se o interpretador Python correto está configurado. Clique na opção do interpretador Python na barra inferior do **vscode**, ao lado da palavra `Python`. O correto seria algo como `.'venv/':poetry`.
-   Se não estiver assim, clique e configure.
-   Opcionalmente, configure a variavel `Venv Path` nos configurações do **vscode**. Tecle `Control+,` e procure por `venv`.
-   Com essas configurações feitas, feche todos os terminais e abra novamente. O ambiente virtual deve ser ativado automaticamente cada vez que você abrir um terminal a partir de agora.

# Aula 2 - Colocando o projeto no **github**

## Colocando o projeto no **github**

Antes de mais nada, seguem **3 regras** a serem consideradas ao seguir as instruções:

-   **Antes de clicar ou responder, leia atentamente as instruções.**
-   **Leia atentamente as instruções antes de clicar ou responder.**
-   **Nunca clique ou responda sem antes ler atentamente as instruções.**

As 3 regras falam a mesma coisa? Sim, você entendeu o recado. ;-)

**Configure o projeto git**

-   Verifique se já não existe uma conta conectada ao github no **vscode**, clicando no ícone **Contas** na barra lateral esquerda. Deve ser o penúltimo ícone da baixo pra cima. Se houver, **desconecte primeiro**.
-   Inicialize o repositório **git**. Clique no ícone do **git** no painel lateral esquerdo. Deve ser o segundo ícone, de cima pra baixo. Opcionalmente, tecle (`Control+Shift+G`). Depois, clique no botão `Initialize repository`.
-   Se aparecer uma bolinha azul no ícone do git com um número, o repositório foi ativado. Esse número indica o número de arquivos que foram criados ou alterados.

**Configure as variáveis do git**

Para isso, digite no terminal, substituindo por suas informações pessoais (colocando as suas informações no lugar):

    git config user.name "Marco André Mendes"
    git config user.email "marcoandre@gmail.com"

Para verificar se as informações estão corretas, digite:

    git config -l

**Crie o arquivo `.gitignore`**

-   Vá no site [gitignore.io](https://gitignore.io/)
-   Escolha as opções `python` e `VisualStudioCode`.
-   Clique em `Criar`.
-   Selecione todo o texto (`Control+A`) e copie (`Control+C`).
-   Crie um arquivo novo na raiz do projeto e dê o nome de `.gitignore`.
-   Cole o conteúdo copiado (`Control+V`).

**Faça a publicação**

-   Escreva uma descrição para o commit (`"commit Inicial"`).
-   Tecle `Control+ENTER` para fazer o envio para o servidor do github.
-   Leia atentamente as instruções relacionadas a autenticação no **github** e criação do projeto.
-   Ao final, seu projeto será incluído no **github** e você poderá visulizá-lo lá.

**Fazendo alterações no projeto e enviando novamente**

Vamos agora realizar algumas mudanças no projeto e enviá-lo novamente para o **github**.

-   Abra um arquivo `.py` (Um atalho útil é teclar `Control+P` e então digitar o nome do arquivo.)
-   Selecione todo o texto (`Control+A`) e mande formatar o código (`Control+Shift+I` ou `Control+Shift+P+"Formatar o Documento"`).
-   Deve aparecer uma mensagem pedindo para instalar um **formatador de código** (`black`). Concorde com a instalação.
-   Após a instalação, execute o comando anterior novamente. O arquivo deve ser formatado.
-   Altere outros arquivos, se houverem.
-   Nesse ponto, você já deve ter vários arquivos modificados.
-   Vá para a aba do **github** no **vscode** e coloque o nome do **commit** como sendo `Instalação do black`.
-   Confirme o **commit** teclando `Control+ENTER`.
-   Faça o envio (`push`), clicando no ícone de envio.
-   Vá no seu projeto no github, atualize a página e verifique as modificações.

**Baixando novamente o projeto**

Agora que seu projeto está no **github**, você pode baixá-lo onde quiser. Vamos testar isso.

-   Apague todo o projeto do seu computador (_isso mesmo, coragem_).
-   Crie novamente uma pasta vazia para hospedá-lo.

-   Abra o **vscode** na pasta (_Você já sabe fazer isso. Aula 1, lembra?_).
-   Vá no projeto no **github**, clique no botão **Code** e copie a url dele. Deve ser algo no seguinte formato: `https://github.com/marrcandre/projeto.git`
-   Tecle `Control+Shift+P+"Git Clone"`
-   Ao ser solicitado o endereço do projeto, informe a url que você copiou de lá.
-   Se tudo correu bem, o projeto foi baixado e está no seu computador.
-   Abra um terminal.
-   Reinstale os pacotes necessários para o seu projeto e ative o ambiente virtual:

Digite no terminal:

    poetry install && poetry shell

-   Feito isso, execute o servidor do seu projeto e teste no navegador.

Pronto! Seu projeto está de volta no computador e rodando.
