# Imersão DevOps - Alura Google Cloud

Este projeto é uma API desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas em uma instituição de ensino. A aplicação foi containerizada com Docker para simular ambientes reais, eliminando o clássico problema do "na minha máquina funciona".

## Pré-requisitos

- [Python 3.10 ou superior instalado](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/get-started/)
- Extensão Gemini Code Assist (opcional para apoio com IA)


## Dia 1: subindo o projeto

1. **Faça o download do repositório:**
   [Clique aqui para realizar o download](https://github.com/guilhermeonrails/imersao-devops/archive/refs/heads/main.zip)

2. **Crie um ambiente virtual:**
   ```sh
   python3 -m venv ./venv
   ```
   No meu windows, usei python -m venv ./venv

3. **Ative o ambiente virtual:**
   - No Linux/Mac:
     ```sh
     source venv/bin/activate
     ```
   - No Windows, abra um terminal no modo administrador e execute o comando:
   ```sh
   Set-ExecutionPolicy RemoteSigned
   ```

     ```sh
     venv\Scripts\activate
     ```

4. **Instale as dependências:**
   ```sh
   pip install -r requirements.txt
   ```

5. **Execute a aplicação:**
   ```sh
   uvicorn app:app --reload
   ```

6. **Acesse a documentação interativa:**

   Abra o navegador e acesse:  
   [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

   Aqui você pode testar todos os endpoints da API de forma interativa.

---

## Estrutura do Projeto

📦 imersao-devops/
├── app.py                      # Arquivo principal da aplicação FastAPI
├── models.py                   # Modelos do banco de dados (SQLAlchemy)
├── schemas.py                  # Schemas de validação (Pydantic)
├── database.py                 # Configuração da conexão com SQLite
├── routers/                    # Rotas organizadas por recurso (alunos,cursos, matrículas)
├── requirements.txt            # Lista de dependências do projeto
├── escola.db                   # Banco de dados SQLite criado automaticamente
├── assets/                     # Arquivos estáticos do projeto (imagens, diagramas, etc.)
│   ├── screenshots/            # Prints da API, interface Swagger, etc.
│   └── diagrams/               # Diagramas de arquitetura e estrutura       
└── README.md                   # Documentação do projeto


---

## Observações

- O banco de dados SQLite será criado automaticamente como `escola.db` na primeira execução.
- Para reiniciar o banco, basta apagar o arquivo `escola.db` (isso apagará todos os dados).

---

## Resultado

![API rodando no ambiente virtual local](api-docs-localhost.png)


## Arquitetura do Projeto (versão local)

                       ┌────────────────────┐
                       │     Usuário        │
                       │ (Navegador/Client) │
                       └────────┬───────────┘
                                │
                                ▼
                    ┌────────────────────────┐
                    │     FastAPI (app.py)   │
                    │  ────────────────────  │
                    │  Rotas (routers/)      │
                    │  Schemas (schemas.py)  │
                    │  Models (models.py)    │
                    │  DB (database.py)      │
                    └───────────┬────────────┘
                                │
                                ▼
                 ┌────────────────────────────┐
                 │    Banco de Dados SQLite   │
                 │        (escola.db)         │
                 └────────────────────────────┘


## Futuro com Docker

                    ┌──────────────────────────────────────┐
                    │              Docker                  │
                    └──────────────────────────────────────┘
                          │                      │
          ┌───────────────┘                      └──────────────┐
          ▼                                                     ▼
┌──────────────────────────────┐           ┌──────────────────────────────┐
│     Container: FastAPI       │           │  Container: SQLite (local)   │
│ (app.py, routers, models...) │           │   (ou possível Postgres)     │
└────────────┬─────────────────┘           └────────────┬─────────────────┘
             │                                          │
             ▼                                          ▼
     Acesso via navegador                       Volume persistente (opcional)



## Criando com Docker

1. Criar Dockerfile com instruções de build

2. Criar .dockerignore para ignorar arquivos desnecessários

3. Construir a imagem Docker:
```bash
 docker build -t api .
```

4. Executar a imagem:
```bash
 docker run -d -p 8000:8000 api
```

## Referências
- [Documentação Oficial do Docker](https://docs.docker.com/reference/dockerfile/)







Referências
https://docs.docker.com/reference/dockerfile/
