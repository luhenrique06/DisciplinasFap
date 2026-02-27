# Banco de Dados - 

**🔗 Link anotações das aulas:** [https://excalidraw.com/#room=729fc2e227957f5986ce,cad5KhDJEB2PVLj87NtvAw](Excalidraw)

---

Bem-vindos ao desafio prático do 1º Bimestre da disciplina de **Laboratório de Banco de Dados** do curso de **Sistemas de Informação** da **Faculdade de Apucarana (FAP)**.

**Professor:** Dr. Luiz Henrique Custódio Mendes Marques 
 **Ano Letivo:** 2026/1 

---

## 🎟️ O Desafio: "Rock in Apucarana" - Concorrência em Vendas

Você foi contratado para projetar o banco de dados do maior festival de música da região. O problema? Os ingressos são escassos e a demanda é gigantesca. Quando as vendas abrirem, milhares de usuários tentarão comprar o mesmo ingresso no exato mesmo milissegundo.

Seu objetivo é modelar o esquema e implementar o controle de concorrência utilizando os recursos avançados do **PostgreSQL**. Se a sua transação falhar, a empresa vende o mesmo assento duas vezes (ferindo os princípios ACID) ou o banco trava completamente com *Deadlocks*.

### 🛑 Regras Gerais
1. **Trabalho em Equipe:** Formem grupos de até **4 pessoas**.
2. **SGBD Oficial:** O uso do **PostgreSQL** é obrigatório. 
3. **Foco no Banco:** Não haverá código de aplicação (Backend/Frontend) sendo avaliado neste bimestre. O foco é 100% no banco de dados. Toda a lógica de reserva deve ser resolvida com SQL, Constraints e Controle de Transações.

---

## 📅 Cronograma de Entregas

### 📦 Entrega 1: Modelagem e SQL Avançado (Avaliação Formativa 1)
**Data de Entrega:** 27/03/2026 
**Objetivo:** Criar o esquema físico e as consultas analíticas.
* **Requisitos:** * Scripts DDL para criar as tabelas (Eventos, Setores, Assentos/Ingressos, Clientes e Reservas) respeitando as regras de Normalização.
  * Uso correto de Primary Keys, Foreign Keys, e Constraints de unicidade.
  * Criação de pelo menos duas *Views* utilizando **JOINs avançados e subconsultas correlacionadas** (ex: Relatório de Ocupação por Setor e Relatório de Receita).
* **Critério de Aceite:** O professor executará o script SQL limpo e inserirá uma carga inicial de dados de teste sem erros. As *Views* devem retornar os resultados corretos.

### 🚦 Entrega 2: Transações e Isolamento (Avaliação Formativa 2)
**Data de Entrega:** 10/04/2026
**Objetivo:** Implementar a lógica de reserva garantindo as propriedades ACID.
* **Requisitos:**
  * Criar um script SQL (ou *Stored Procedure*) que simula a compra de um ingresso.
  * A transação deve: Verificar se o assento está livre, associá-lo ao cliente e abater o valor do limite do cliente. Tudo ou nada (Atomicidade).
  * Vocês devem utilizar mecanismos explícitos de *Locks* (ex: `SELECT ... FOR UPDATE`) para evitar condições de corrida.
* **Critério de Aceite:** O professor abrirá duas abas do *PgAdmin* e executará a mesma transação simultaneamente. O banco não pode permitir o *overbooking*.

### ⚔️ Entrega 3: Sobrevivendo aos Deadlocks (Avaliação Bimestral)
**Data de Entrega:** 24/04/2026 
**Objetivo:** Teste de estresse com alta concorrência.
* O banco de dados do grupo será colocado à prova. 
* Vamos rodar um script que criará 500 conexões simultâneas com o seu PostgreSQL. Todas tentarão comprar os mesmos 100 ingressos de um setor específico.
* **Critério de Aceite e Pontuação:**
  1. **Integridade de Dados (ACID):** Foram vendidos exatamente 100 ingressos? Nenhum cliente ficou com saldo negativo? (Eliminatório).
  2. **Performance e Deadlocks:** O banco travou? Quantas transações foram abortadas por *deadlock* e quantas foram resolvidas com sucesso?. 

---

## 🛠️ Como Submeter
2. Crie uma pasta com o nome/RA do grupo.
3. Todo o código deve estar na forma de scripts `.sql` numerados (ex: `01_schema.sql`, `02_views.sql`, `03_transactions.sql`).
