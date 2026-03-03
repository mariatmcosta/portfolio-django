# Portfólio Web - 2026
Site para Portfólio Web Profissional - 2026

Sistema web desenvolvido com Django para apresentação de portfólio profissional, incluindo modelagem de projetos, tecnologias utilizadas e estrutura para mensagens de contato.

## Sobre o Projeto
Este projeto consiste em uma aplicação web desenvolvida com o framework Django, utilizando arquitetura MVT (Model–View–Template).
O sistema foi estruturado para:
- Apresentar informações profissionais;
- Organizar projetos desenvolvidos;
- Associar projetos a tecnologias;
- Estruturar recebimento de mensagens de contato;
- Manter base relacional preparada para expansão futura (CRUD e API REST);
Atualmente, a aplicação realiza renderização server-side e possui estrutura completa de banco de dados, pronta para integração dinâmica.

---

## Tecnologias Utilizadas
Backend:
-	Python
-	Django
-	PostgreSQL (produção)
-	SQLite (desenvolvimento)
-	Gunicorn
-	WhiteNoise

Frontend:
-	HTML
-	Tailwind CSS
-	JavaScript (Vanilla JS)

Infraestrutura:
-	dj-database-url
-	python-dotenv
-	psycopg2-binary

---

## Estrutura do Projeto
```
portfolio-django/
│
├── config/
│   ├── __init__.py
│   ├── asgi.py       
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│
├── core/
│   ├── migrations/
│       ├── 0001_initial.py
│       ├── __init__.py
│   ├── templates/
│       ├── core/
│           ├── home.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   ├── views.py
│
├── node_modules/
│   ├── ...
│
├── static/
│   ├── css/...
│   ├── cv/...
│   ├── relatorios/...
│   ├── sounds/...
│   ├── .DS_Store
│
├── staticfiles/
│   ├── admin/...
│   ├── css/...
│   ├── cv/...
│   ├── relatorios/...
│   ├── sounds/...
│
├── templates/
│   ├── base.html
│
├── .DS_Store
├── .gitignore
├── README.md
├── manage.py
├── package-lock.json
├── package.json
├── requirements.txt
```

---


## Guia de Execução Local
1. Clonar o repositório
```
git clone <url-do-repositorio>
cd portfolio-django
```
2. Criar ambiente virtual
```
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```
3. Instalar dependências
```
pip install -r requirements.txt
```
4. Aplicar migrações
```
python manage.py migrate
```
5. Executar servidor local
```
python manage.py runserver
```
6. A aplicação estará disponível em: http://127.0.0.1:8000/

---

## Arquitetura de Dados
O sistema utiliza o ORM do Django para modelagem relacional.

Principais Entidades:

Usuario:
-	nome
-	email
-	bio
-	foto_url

Tecnologia:
-	nome

Projeto:
-	titulo
-	descricao
-	imagem_url
-	github_url
-	data_criacao
-	usuario (ForeignKey)
-	tecnologias (ManyToMany)

MensagemContato:
-	nome
-	email
-	mensagem
-	data_envio

---

## Diagrama da Arquitetura de Dados
```
Usuario
   │ 1
   │
   │ N
Projeto ─────────── N Tecnologia
   │
   │
MensagemContato (entidade independente)
```
Relações:
-	Um Usuario pode possuir vários Projetos
-	Um Projeto pode utilizar várias Tecnologias
-	MensagemContato é uma entidade independente

---

## Fluxo de Arquitetura da Aplicação
```
Cliente (Browser)
        ↓
URL Dispatcher (config/urls.py)
        ↓
App Routing (core/urls.py)
        ↓
View (core/views.py)
        ↓
Template HTML
        ↓
Resposta HTTP
```

---

## Possíveis Melhorias Futuras
- 	Implementação de CRUD completo
-	Criação de API REST com Django REST Framework
-	Integração AJAX para consumo dinâmico de dados
-	Registro dos modelos no Django Admin
-	Implementação de autenticação personalizada
-	Deploy com Docker
-	CI/CD

---

## Tipo de Arquitetura
- Monolítica
- Server-Side Rendered
- MVT (Model-View-Template)
- ORM Relacional

---

## Autora: Maria Eduarda Taveiros Martins Costa
Projeto desenvolvido como portfólio técnico, proposto como projeto pela Healthtech Júnior Einstein.

