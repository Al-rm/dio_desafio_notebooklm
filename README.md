# 🧠 Caderno Temático: Microservices com Python e FastAPI

## 📌 Contexto e Objetivos

**Assunto escolhido:**  
Construção de microsserviços utilizando Python e o framework FastAPI.

**Por que este tema?**  
Microsserviços são uma arquitetura essencial para sistemas modernos escaláveis. FastAPI é um dos frameworks Python mais rápidos e produtivos para criar APIs, com suporte nativo a assincronia, documentação automática e validação de dados via Pydantic.

**Objetivos de estudo:**  
- Compreender os princípios da arquitetura de microsserviços.  
- Aprender a construir, testar e documentar microsserviços com FastAPI.  
- Identificar padrões de comunicação (REST, mensageria).  
- Conhecer boas práticas de deploy e orquestração (Docker, Kubernetes).  
- Consolidar um guia rápido de referência para projetos futuros.

---

## 📚 Curadoria de Fontes

> Fontes utilizadas no NotebookLM (vídeos do YouTube + documentações oficiais).

### 🎥 Vídeos Tutoriais (YouTube)

| # | Título do Vídeo | Canal | Link |
|---|----------------|-------|------|
| 1 | Learn Fast API With This ONE Project | Tech With Tim | [Assistir](https://www.youtube.com/watch?v=SR5NYCdzKkc) |
| 2 | Python FastAPI Tutorial (Part 2): HTML Frontend for Your API | Corey Schafer | [Assistir](https://www.youtube.com/watch?v=G4NIB9Rx9Qs) |
| 3 | How to build a python microservice with fastapi | 马克的技术工作坊 | [Assistir](https://www.youtube.com/watch?v=QRrSfDKjqdE) |
| 4 | How to build a FastAPI app with PostgreSQL | Code with Josh | [Assistir](https://www.youtube.com/watch?v=398DuQbQJq0) |
| 5 | Python FastAPI Tutorial (Part 15): PostgreSQL and Alembic | Corey Schafer | [Assistir](https://www.youtube.com/watch?v=e8NnDz8uT7o) |
| 6 | **Playlist:** FastAPI Tutorials | Corey Schafer | [Acessar](https://www.youtube.com/playlist?list=PL-osiE80TeTsak-c-QsVeg0YYG_0TeyXI) |

### 📄 Documentações Oficiais

| # | Documentação | Link |
|---|--------------|------|
| 7 | FastAPI | [fastapi.tiangolo.com](https://fastapi.tiangolo.com/) |
| 8 | Pydantic | [pydantic.dev/docs](https://pydantic.dev/docs/) |
| 9 | Alembic | [alembic.sqlalchemy.org](https://alembic.sqlalchemy.org/en/latest/) |
| 10 | PostgreSQL | [postgresql.org/docs](https://www.postgresql.org/docs/) |

---

## 🧪 Engenharia de Prompts – "Cicatrizes"

Aqui documentei as perguntas que fiz ao NotebookLM, as respostas obtidas e como refinei os prompts.

### ✅ Pergunta 1 – Estrutura de Projeto

**Prompt:** *"What are the best practices for structuring a FastAPI project?"*

**Resposta obtida:** A IA destacou modularidade, separação de responsabilidades (Service Layer), uso de APIRouter, e preparação para produção com Alembic e PostgreSQL.

**Aprendizado:** O ponto mais valioso foi a recomendação de separar a lógica de negócio em uma camada de serviços – algo que muitos tutoriais ignoram.

---

### ✅ Pergunta 2 – Segurança no FastAPI

**Prompt:** *"What are the advantages of using a FastAPI with regard to project security?"*

**Resposta obtida:** FastAPI oferece OAuth2 integrado, validação automática com Pydantic, controle de exposição via `response_model`, e middlewares para CORS/CSRF.

**Aprendizado:** Descobri que `response_model` não é apenas conveniência, mas um recurso crítico de segurança para evitar vazamento acidental de dados.

---

### 🔧 Dificuldades e ajustes

| Problema | Solução |
|----------|---------|
| Resposta genérica sobre microsserviços | Adicionei "com exemplos em FastAPI" ao prompt |
| IA focou apenas em comunicação síncrona | Pedi explicitamente "inclua mensageria assíncrona" |
| Glossário inicial incompleto | Solicitei termos específicos (Dependency Injection, Event-Driven) |

---

## 📘 Miniguia de Estudo (Entrega Final)

### 🔹 Resumo Rápido

**FastAPI** = framework moderno + rápido + baseado em type hints.

**Para que serve?** Construir APIs e microsserviços com Python.

**Principais vantagens:**
- Alta performance (comparável a Node.js e Go)
- Documentação automática (Swagger UI)
- Validação de dados com Pydantic
- Suporte nativo a `async/await`

---

### 🔹 Estrutura de Projeto Recomendada
      meu-projeto/
      ├── app/
      │ ├── main.py # Inicializa o app
      │ ├── routers/ # Endpoints (APIRouter)
      │ ├── models/ # Banco de dados (SQLAlchemy)
      │ ├── schemas/ # Validação (Pydantic)
      │ ├── services/ # Lógica de negócio
      │ └── config.py # Configurações
      ├── tests/ # Testes
      ├── .env # Variáveis de ambiente
      └── requirements.txt

---

### 🔹 Segurança Essencial

| Prática | Como fazer |
|---------|-------------|
| Autenticação | `OAuth2PasswordBearer` + JWT |
| Proteger saída de dados | `response_model` (filtra campos sensíveis) |
| CORS | `CORSMiddleware` |
| Secrets | `.env` + Pydantic Settings |

---

### 🔹 Banco de Dados

| Ambiente | Banco | Migrações |
|----------|-------|-----------|
| Desenvolvimento | SQLite | `create_all()` |
| Produção | PostgreSQL | Alembic |

---

### 🔹 Glossário (conceitos-chave)

| Termo | Significado |
|-------|-------------|
| **APIRouter** | Divide as rotas em múltiplos arquivos |
| **Pydantic** | Valida dados com type hints |
| **Alembic** | Gerencia migrações de banco |
| **response_model** | Filtra o que a API retorna (segurança) |
| **Dependency Injection** | Injeta DB, auth, etc. nas rotas |

---

🧠 Reflexão final

Este projeto me ensinou que:
```text
    - A curadoria de fontes é tão importante quanto o uso da IA.
    - A engenharia de prompts exige tentativa, erro e refinamento (as cicatrizes são valiosas).
    - O NotebookLM é uma ferramenta poderosa para consolidar conhecimento, desde que você saiba perguntar.
```
---
