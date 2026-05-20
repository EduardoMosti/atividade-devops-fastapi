\# Atividade DevOps FastAPI



Projeto desenvolvido para atividade prática de DevOps utilizando uma API construída com FastAPI, testes automatizados, Docker e pipeline de integração contínua com GitHub Actions.



\## Objetivo



O objetivo do projeto é demonstrar o ciclo básico de uma aplicação Python com práticas de DevOps, incluindo:



\- criação de uma API REST;

\- execução local da aplicação;

\- validação de endpoints;

\- testes automatizados;

\- criação de imagem Docker;

\- execução de pipeline no GitHub Actions.



\## Tecnologias utilizadas



\- Python 3.12

\- FastAPI

\- Uvicorn

\- Pytest

\- Flake8

\- Docker

\- GitHub Actions



\## Estrutura do projeto



```text

atividade-devops-fastapi/

├── .github/

│   └── workflows/

│       └── python-app.yml

├── app/

│   ├── \_\_init\_\_.py

│   └── main.py

├── tests/

│   └── test\_main.py

├── Dockerfile

├── README.md

├── requirements.txt

└── .gitignore

```



\## Endpoints da API



\### Rota principal



```http

GET /

```



Retorno esperado:



```json

{

&#x20; "status": "ok",

&#x20; "message": "API rodando!"

}

```



\### Health check



```http

GET /health

```



Retorno esperado:



```json

{

&#x20; "status": "healthy"

}

```



\### Criar item



```http

POST /items

```



Exemplo de corpo da requisição:



```json

{

&#x20; "name": "Produto Teste",

&#x20; "price": 10.5

}

```



\## Como executar localmente



Crie o ambiente virtual com Python 3.12:



```bash

py -3.12 -m venv venv

```



Ative o ambiente virtual:



```bash

venv\\Scripts\\activate

```



Instale as dependências:



```bash

python -m pip install -r requirements.txt

```



Execute a aplicação:



```bash

uvicorn app.main:app --reload --port 8080

```



Acesse no navegador:



```text

http://127.0.0.1:8080

```



Documentação automática da API:



```text

http://127.0.0.1:8080/docs

```



\## Como executar os testes



```bash

python -m pytest tests/ -v

```



\## Como validar a sintaxe



```bash

flake8 app tests --count --select=E9,F63,F7,F82 --show-source --statistics

```



\## Como executar com Docker



Criar a imagem Docker:



```bash

docker build -t atividade-devops-fastapi .

```



Executar o container:



```bash

docker run -p 8080:8080 atividade-devops-fastapi

```



Acessar:



```text

http://127.0.0.1:8080

```



\## Pipeline DevOps



O projeto possui um pipeline configurado no GitHub Actions.



O pipeline executa as seguintes etapas:



1\. Baixa o código do repositório.

2\. Configura o Python 3.12.

3\. Instala as dependências do projeto.

4\. Executa validação de sintaxe com Flake8.

5\. Executa os testes automatizados com Pytest.

6\. Valida a construção da imagem Docker.



O arquivo do pipeline está localizado em:



```text

.github/workflows/python-app.yml

```



\## Status da aplicação



A aplicação foi validada localmente e também pelo pipeline automatizado do GitHub Actions.

