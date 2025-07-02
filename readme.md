# 📦 API Escolar – CI/CD com Docker e GitHub Actions

Este projeto foi desenvolvido como parte da **Imersão Cloud DevOps**, evolução do repositório [`api-escolar-fastapi-docker`](https://github.com/ronayrton/api-escolar-fastapi-docker), com foco em práticas modernas de **DevOps** como **Integração Contínua (CI)** e **Entrega Contínua (CD)**.

---

## 🚀 Objetivos

- Automatizar o ciclo de vida da aplicação com GitHub Actions
- Construir imagens Docker com boas práticas (sem usar `latest`)
- Utilizar Docker Compose com volumes persistentes
- Organizar o projeto com workflows no padrão `.github/workflows`
- Integrar práticas recomendadas com apoio de **IA**

---

## 🧰 Tecnologias e ferramentas

- **FastAPI**
- **Docker & Docker Compose**
- **GitHub Actions**
- **CI/CD com pipelines**
- **Volumes persistentes**
- **Boas práticas orientadas**
- **.github/workflows/main.yml**
- **Extensão Gemini Code Assist (Google AI)**

---

## 🤖 IA na prática

Utilizei a **Extensão Gemini Code Assist** para:

- Sugerir boas práticas no `Dockerfile`
- Auxiliar na criação do `docker-compose.yml`
- Gerar partes do workflow `.github/workflows/main.yml`
- Validar variáveis de ambiente e organização da pipeline

---

## 📦 Funcionalidades

- Criação de uma aplicação containerizada com Docker-compose
- Evitar o uso da imagem `:latest` para garantir consistência e previsibilidade
- Pipeline automatizada com GitHub Actions para:
  - Build da imagem Docker
  - Execução de testes automatizados
  - Deploy automatizado (simulado ou real)
- Estrutura `.github/workflows` bem definida e comentada


## 🔁 CI/CD com GitHub Actions

Workflow automatizado para:

- 🔨 Build da imagem
- ✅ Validação e testes (mock)
- 🚀 Deploy (simulado)
- 🔐 Uso de secrets e variáveis

Local: `.github/workflows/main.yml`

---

## 🧪 Execução local

```bash
git clone https://github.com/seu-usuario/api-escolar-ci-cd-github-actions.git
cd api-escolar-ci-cd-github-actions
docker-compose up -d
```
Acesse a API em: http://localhost:8000


## 🚀 GitHub Actions
Veja o workflow em .github/workflows/pipeline.yml. Ele é responsável por:

- Construir a imagem com docker build

- Validar o código e rodar testes

- Subir a imagem (caso real) para o DockerHub ou GitHub Container Registry

- Enviar alertas ou logs de execução


