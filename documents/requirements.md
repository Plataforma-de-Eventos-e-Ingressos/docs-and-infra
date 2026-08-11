# 📋 Levantamento de Requisitos - Plataforma de Eventos

Este documento descreve os requisitos funcionais, não funcionais, regras de negócio e os limites de escopo para o Produto Mínimo Viável (MVP) do desafio Elite Dev[cite: 1].

## 👥 Atores do Sistema

O sistema contará com três perfis de acesso distintos com diferentes permissões:
1. **Organizador:** Responsável por criar e gerenciar os eventos.
2. **Cliente:** Usuário final que navega, reserva, realiza o pagamento simulado e acessa o ingresso.
3. **Portaria:** Responsável exclusivo por validar os ingressos na entrada do evento.

---

## ⚙️ Requisitos Funcionais (RF)

Os Requisitos Funcionais descrevem as ações que o sistema deve ser capaz de executar[cite: 1].

* **RF-01 | Integração de Catálogo:** O sistema deve consumir a API externa (TMDb ou Ticketmaster) para popular o catálogo de shows ou filmes disponíveis para criação.
* **RF-02 | Gestão de Eventos:** O Organizador deve poder criar e gerenciar eventos, definindo data, local, capacidade total e preço.
* **RF-03 | Vitrine de Eventos:** O Cliente deve poder navegar e buscar eventos publicados, visualizando data, local e preço.
* **RF-04 | Fluxo de Reserva:** O sistema deve permitir que o Cliente escolha a quantidade de ingressos (pista) ou selecione um lugar em um mapa de assentos (cinema/teatro).
* **RF-05 | Checkout Simulado:** O sistema deve possuir um fluxo de pagamento simulado, que contemple cenários de confirmação e de recusa.
* **RF-06 | Área do Cliente:** O sistema deve possuir uma área "Meus Ingressos" exibindo o ingresso adquirido e seu respectivo QR Code.
* **RF-07 | Compartilhamento:** O sistema deve gerar um link para que o Cliente possa compartilhar seu ingresso.
* **RF-08 | Leitura de Ingressos:** A interface da Portaria deve permitir a leitura do QR Code pela câmera ou a digitação manual do código do ingresso.
* **RF-09 | Feedback de Validação:** A tela da portaria deve exibir um retorno claro ao validar o código: válido, inválido, já utilizado ou evento errado.

---

## 🔒 Regras de Negócio (RN)

As Regras de Negócio são as condições críticas que garantem a integridade da plataforma.

* **RN-01 | Concorrência de Assentos:** O sistema deve garantir, a nível de banco de dados e aplicação, que o mesmo lugar/ingresso não seja vendido duas vezes.
* **RN-02 | Segurança do Ingresso:** O ingresso deve ser gerado com um código QR criptografado/único (ex: JWT) que não possa ser forjado por terceiros.
* **RN-03 | Prevenção de Dupla Entrada:** A validação na portaria deve garantir que um mesmo ingresso não seja validado (utilizado) duas vezes.

---

## 🚫 Fora de Escopo

* Emissão de nota fiscal.
* Sistema de revenda de ingressos entre usuários.
* Desenvolvimento de aplicativo mobile nativo.
* Fluxo de recuperação de senha.
* Envio de ingressos por e-mail.
