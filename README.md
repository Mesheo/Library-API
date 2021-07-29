>Todo o conteúdo desse readme foi escrito beaseado nesse <a href="https://www.youtube.com/watch?v=wtl8ZyCbTbg&list=PLcM_74VFgRhpyCtsNXyBUf27ZRbyQnEEb">vídeo.</a> Espero que você aprenda algo novo!

# API para uma biblioteca
>O python facilita bastante coisas para a gente, como os serializers (que convertem objetos para strings na comunicação cliente-servidor) e os verbos http (GET, POST, PUT, DELETE) que de certa forma também vem por padrão. Não me aprofundei neles durante o readme porque também preciso entender melhor como essas coisas funcionam

* [Introdução](#introdução)
* [Preparando o Ambiente](#preparando-o-ambiente)
* [Projeto x App](#projeto-app)
* [Criando os modelos](#criando-os-modelos)
* [Pasta API](#pasta-api)
* [Criacao das rotas](#criacao-das-rotas)

# Introdução
A ideia do projeto é que possamos armazenar livros e seus atributos dentro de um banco de dados e gerenciar tudo isso sem precisar de uma interface gráfica. Assim, outra aplicação poderá se comunicar com a nossa de forma eficiente. Esse é o conceito de API (Aplication Programming Interface)

# Preparando o ambiente
Aqui temos a receita de bolo pra deixar a sua máquina pronta para levantar um servidor usando o django e receber aquele 200 bonito na cara

```bash
python -m venv venv #criando ambiente virtual na sua versao do python
./venv/Scripts/Activate.ps1 #Ativando o ambiente virtual
pip install django djangorestframework #instalação local das nossas dependências
```
A graça do ambiente virtual é que todas as suas dependências (e no python costumam são muitas) ficam apenas num diretório específico. Logo, você pode criar projetos que usam versões diferentes da mesma biblioteca sem que haja conflito na hora do import.

### Projeto x App
Ainda no terminal usamos os proximos comandos para criar o `project` que vai carregar nosso `app`. No django cada project pode carregar multiplos apps, como um site de esportes que pode ter um app para os artigos, outro para rankings etc.
```bash
django-admin startproject library . #ponto indica diretório atual
django-admin startapp books
python manage.py runserver #pra levantarmos o servidor local com a nossa aplicação
```
Sua estrutura de pastas deve estar assim:

![imagem da estrutura](img/imagem-estrutura.jpg)

Para criar as tabelas no banco de dados (Por enquanto *Sqlite3*) executamos o comando
```bash
python manage.py migrate
```
E isso evita que as unapplied migrations apareça na próxima vez que você levantar o servidor 

![imagem unaplied](img/unapplied.png)






