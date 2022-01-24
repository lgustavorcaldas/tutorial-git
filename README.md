# <p align = "center"> 📗 Introdução ao Git & GitHub</p>

[GitHub](https://github.com/) é uma plataforma de hospedagem de código-fonte e arquivos com controle de versão usando o [Git](https://git-scm.com/docs/git/pt_BR). Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo.




## <p align = "left"> 🔻 Instalação </p>

#### <p align = "left"> Windows </p>

- GitHub Bash : https://git-scm.com/download/win
- GitHub Desktop : https://desktop.github.com/

#### <p align = "left"> Linux </p>

```bash
$ sudo apt-get update
$ sudo apt-get install git
```
<br/>

## <p align = "left"> 🔻 Configuração inicial </p>


```bash
$ git config --global user.name "Fulano de tal"
$ git config --global user.email "fulano@email.com.br"
```
<br/>

## <p align = "left"> 🔻 Primeiro repositório </p>

### 🌎 Repositório Remoto 
- No canto superior direito de qualquer página, use o menu suspenso  `+`  e selecione <strong>Novo repositório.</strong>

<p align="center"><img src="https://user-images.githubusercontent.com/72531277/134835276-75b8ef7f-99ee-4d15-bd79-fd18ba6f484e.png" /> </p>

<br/>
- Digite um nome curto e memorável para o seu repositório, por exemplo, "Hello-World". Inserir a descrição é opcional. Você tbm pode definir a <strong>visibilidade</strong> do seu repositório ou incluir algum arquivo padrão ou licença de uso. Após definidas as configurações é só clicar no botão verde ao final da tela: <strong> Criar Repositório</strong>

### 📍 Repositório Local

Na sua máquina local, você deve fazer os seguinte passos no terminal (utilize o Git Bash se tiver no Windows):

- Crie a pasta local e navegue até ela

```bash
 $ mkdir Nome-do-Projeto
 $ cd Nome-do-projeto
 ```
 <br/>

- Inicialize o git no repositório

 ```bash
 $ git init 
 ```
<br/>

- Crie um arquivo inicial.

ps: caso deseje enviar algum trabalho pro github, você pode mover ou colar seus arquivos aqui dentro.

 ```bash
 $ touch README.md
 ```
 <br/>

- Adicione qualquer aquivo novo ou que foi modificado com o comando: 
 ```bash
 $ git add .
 ```
 <br/>


- Digite um comentário breve sobre as modificações feitas no repositorio.
 ```bash
 $ git commit -m 'Seu comentário'
 ```
 <br/>

 
- (dica) Renomeie a `branch` atual para main 
 ```bash
 $ git branch -M main
 ```
 <br/>


- Especifique o endereço do repositório remoto.
 ```bash
 $ git remote add origin https://github.com/fulanodetal/meu-primeiro-repositorio.git
 ```
 <br/>

 - Após isso, basta empurrar os arquivos ao servidor remoto:

 ```bash
 $ git push -u origin main
 ```
 <br/>
 
 <p align ="center"> <strong>E pronto, tá feito o sorvetinho!
</a></strong></p>

 <br/>
 <br/>

<p align ="center"> Hei, psiu! Se ta com dúvida sobre a conexão SSH, é só clicar <strong><a href="https://github.com/luanalessa/tutorial-git/blob/main/CONEXAO-SSH.md">aqui</a></strong></p>
