# 🐳 Infraestrutura e Documentação - Plataforma de Eventos (Elite Tickets)

Este repositório centraliza a **infraestrutura e a documentação arquitetural** da plataforma de eventos e ingressos **Elite Tickets**.

A separação entre infraestrutura, documentação e código-fonte permite manter os módulos de **Front-end** e **Back-end** independentes, proporcionando:

* Isolamento de responsabilidades e pipelines de CI/CD mais organizados.
* Registro dos requisitos e decisões arquiteturais antes da implementação.
* Padronização do ambiente de desenvolvimento local por meio do Docker.
* Centralização dos artefatos de planejamento e modelagem do sistema.

---

## 🧠 Artefatos de Planejamento e Decisão

Conforme valorizado no desafio técnico, o processo de desenvolvimento e a tomada de decisões são tão importantes quanto o código final.

Por isso, os artefatos produzidos durante o planejamento — incluindo os insumos refinados em conjunto com Inteligência Artificial — foram versionados neste repositório.

Esses documentos registram a evolução da solução e ajudam a demonstrar **como o sistema foi concebido antes da implementação**.

### 📂 Estrutura do Repositório

| Diretório / Arquivo     | Descrição                                                                                                                                                                                                                            |
| :---------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `📁 design/`            | Contém o planejamento visual da interface. Inclui o `low-fidelity prototype.html`, um wireframe interativo utilizado para mapear a experiência do usuário no ambiente web desktop.                                                   |
| `📁 documents/`         | Centraliza os artefatos de engenharia de software, incluindo o `requirements.md`, com o levantamento de requisitos e casos de uso, e o `data-model.md`, contendo a modelagem do banco de dados e o diagrama entidade-relacionamento. |
| `📄 docker-compose.yml` | Arquivo de orquestração do ambiente local, responsável atualmente por disponibilizar o PostgreSQL utilizado durante o desenvolvimento.                                                                                               |

---

## 🚀 Como Executar a Infraestrutura Local

Para executar a plataforma localmente de forma integrada, o primeiro passo é iniciar a infraestrutura de dados disponibilizada por este repositório.

O **Docker** é utilizado para garantir um ambiente de desenvolvimento padronizado e reproduzível, reduzindo diferenças de configuração entre máquinas.

### 1. Pré-requisitos

Certifique-se de possuir o **Docker** instalado e em execução.

Podem ser utilizados o Docker Desktop ou o Docker Engine, de acordo com o sistema operacional.

### 2. Clone este repositório

Clone o repositório de infraestrutura e navegue até sua pasta raiz:

```bash
git clone https://github.com/Plataforma-de-Eventos-e-Ingressos/docs-and-infra.git
cd docs-and-infra
```

Crie um arquivo `.env` na raiz do projeto:

```env
POSTGRES_USER=exemplo_teste
POSTGRES_PASSWORD=exemplo_teste
POSTGRES_DB=exemplo_tabela
DATABASE_URL=postgresql://exemplo_teste:exemplo_teste@db:5432/exemplo_tabela
```

### 3. Suba os containers

Execute o Docker Compose em modo detached para iniciar os serviços em segundo plano:

```bash
docker-compose up -d
```

### 4. Validação

Após a inicialização, o banco de dados PostgreSQL estará disponível localmente na porta padrão:

```text
localhost:5432
```
Front-end
```text
localhost:80
```
Back-end
```text
localhost:8000
```

A partir desse momento, o **Back-end** pode ser iniciado e configurado para utilizar o PostgreSQL disponibilizado pelo ambiente de infraestrutura.

---

## 🛑 Interrompendo os Serviços

Para parar os serviços e remover os containers:

```bash
docker-compose down
```

Os volumes persistentes não serão removidos por esse comando. Dessa forma, os dados permanecem disponíveis caso estejam configurados em volumes Docker.

Caso seja necessário remover também os volumes:

```bash
docker-compose down -v
```

> ⚠️ O uso de `-v` remove os volumes associados aos serviços e, consequentemente, os dados persistidos neles.

---

## 🔗 Navegação do Ecossistema

Este repositório faz parte do ecossistema da plataforma **Elite Tickets**.

Acesse os demais módulos:

* 💻 **Frontend Web** — Interface web desenvolvida em React.
* ⚙️ **Backend API** — API RESTful desenvolvida em FastAPI.

---

## 👨‍💻 Desenvolvedor

Desenvolvido por **Robson do Amaral Diógenes**.
