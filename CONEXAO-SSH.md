# <p align = "center"> 📗 GitHub - Conexão SSH</p>

 <p align = "center"> Usando o protocolo SSH, você pode  se conectar e autenticar sevidores e serviços remotos. Gerando uma <a href ="https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh"> chave SSH </a> você pode se conectar com o GitHub sem precisar inserir seu usuário e chave de acesso em cada conexão.

</p>

## <p align = "left"> 🔻 Passo a passo para configurar SSH no GitHub via terminal (Git Bash) </p>

1. Gerar chaves pública e privada, usando seu email do GitHub:
```bash
$ ssh-keygen -t ed25519 -C "fulanodetal@email.com"

# Saída : Generating public/private ed25519 key pair.
```
<br/>

2. Confirme os proximo passos, adicionar uma senha a conexão SSH é opcional.
A resposta deverá ser semelhante ao exemplo:
```bash
# Saída : 
Your identification has been saved in /root/.ssh/id_ed25519
Your public key has been saved in /root/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:YzX9kjuahs789ha+mJkOJkU897GfDo36paHg67HnBdAc fulanodetal@email.com

```
<br/>


3. Inicie o ssh-agent
```bash
$ eval "$(ssh-agent -s)"
```
<br/>

4. Adicione a chave privada.
```bash
$ ssh-add /root/.ssh/id_ed25519
```
⚠️ Se não conseguir abrir a conexão para autenticar o agente, rode o seguinte comando e repita o <strong>passo 4</strong>:

```bash
$ exec ssh-agent bash # ou exec ssh-agent zsh

# Saída esperada: Identity added: /root/.ssh/id_ed25519 (lessalsn@gmail.com)

```
<br/>

5. Copie a chave pública:

```bash
$ cat ~/.ssh/id_ed25519.pub

# Saída esperada: ssh-ed25519 YzX9kjuahs789ha+mJkOJkU897GfDo36paHg67HnBdJSAAJSIJIJASIJ8798ASHvgvAc fulanodetal@email.com
```
<br/>

6. Adicione nas configurações do GitHub : `Profile > Settings > SSH and GPG keys`

<p align="center">
 <img src="https://user-images.githubusercontent.com/72531277/135255696-81448db0-6253-48c3-84e9-12de832204cd.png"/>
</p>

7. Teste a conexão:

```bash
$ ssh -T git@github.com
# Saída: Hi fulanodetal! You've successfully authenticated, but GitHub does not provide shell access.
```
<br/>

Pronto, agora quando for adicionar o endereço do  repositório `remoto` , use o protocolo SSH ao invés do HTTPS.

```bash
$ git remote add origin git@github.com:fulanodetal/meuprojeto.git
```
<br/>
<br/>
<p align ="center">
🚩 Aleḿ desses dois protocolos o Git também possui o seu próprio e foi desenvolvido para ter mais velocidade que os outros. Este é o protocolo mais rápido, mas pode ter problemas com firewalls, já que ele utiliza uma porta sem tráfego de rede normalmente.
 </p>
 
```bash
$ git remote add origin git@github.com/fulanodetal/meuprojeto.git
```
 <br/>

<p align ="justify">Neste exemplo, o caminho completo não é especificado. Quando você inicia um servidor Git informa-se qual o diretório para procurar os repositórios, apenas especificando o nome dos mesmos.</p> 

 <p align ="justify">A grande diferença entre o protocolo Git e o SSH, além da encriptação, é que o Git é anônimo. Isto é bom quando se deseja fornecer um acesso público de apenas leitura (ou read-only) ao repositório. Por permitir acesso anônimo este acesso poderia ser perigoso caso o repositório fosse aberto para escrita, por isso tal restrição. Dessa forma, ninguém pode fazer alterações no mesmo quando acessado através do protocolo Git.</p> 

  <p align ="justify">Assim sendo, sempre que se verifica um repositório usando "git://" pode-se afirmar que ele tem acesso apenas à leitura.
Normalmente o que as organizações fazem é permitir que os desenvolvedores utilizem o protocolo Git para fazer um pull, recebendo os arquivos do repositório. Utiliza-se o SSH os desenvolvedores que faze um push, enviando assim as alterações diretamente para o repositório.</p> 

<p align ="right"> <strong>- Via <a href="https://www.devmedia.com.br/trabalhando-com-o-repositorio-remoto-no-git/33786">Dev Media</a></strong></p>
