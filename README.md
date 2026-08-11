Segue o conteúdo formatado e pronto para salvar como `README.md`:

# 🐳 Infraestrutura e Documentação - Elite Tickets

Este repositório centraliza a arquitetura, o planejamento de produto e a orquestração da infraestrutura local para a plataforma de eventos e ingressos do desafio **Elite Dev (Verzel)**.

O objetivo de manter a documentação e a infraestrutura isoladas do código-fonte (Front-end e Back-end) é garantir uma governança clara, facilitando a visualização dos requisitos antes da execução e padronizando o ambiente de desenvolvimento.

---

## 📂 Estrutura do Repositório

| Diretório / Arquivo     | Descrição                                                                                                                                       |
| :---------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------- |
| `📁 design/`            | Contém o planejamento visual da interface. Inclui o `low-fidelity prototype.html`, um wireframe interativo desenhado para ambiente web desktop. |
| `📁 documents/`         | Centraliza as regras de negócio. Contém o `requirements.md` (levantamento de escopo) e o `data-model.md` (diagrama de entidade-relacionamento). |
| `📄 docker-compose.yml` | Arquivo de orquestração local para levantar os serviços auxiliares, como o banco de dados PostgreSQL.                                           |

---

## 🚀 Como Executar a Infraestrutura Local

Para rodar as aplicações (Back-end e Front-end) na sua máquina, é necessário primeiro levantar o banco de dados.

Utilizamos o Docker para garantir que o ambiente seja idêntico para qualquer desenvolvedor.

### Passo a passo

#### 1. Instale e execute o Docker

Certifique-se de que o [Docker Desktop](https://www.docker.com/products/docker-desktop) está instalado e rodando.

#### 2. Clone este repositório

Clone o repositório e navegue até a pasta raiz:

```bash
git clone https://github.com/Plataforma-de-Eventos-e-Ingressos/docs-and-infra
cd docs-and-infra
```

#### 3. Suba os containers

Execute o Docker Compose em segundo plano:

```bash
docker compose up -d
```

#### 4. Acesse o banco de dados

O banco de dados PostgreSQL estará disponível na porta:

```text
5432
```

### 🛑 Interrompendo os serviços

Para interromper e remover os containers, execute:

```bash
docker compose down
```
