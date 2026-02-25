
Bem-vindos ao desafio prático do 1º Bimestre da disciplina de **Sistemas Distribuídos e Computação em Nuvem** do curso de **Sistemas de Informação** da **Faculdade de Apucarana (FAP)**.

**Professor:** Dr. Luiz Henrique Custódio Mendes Marques
**Semestre:** 7º Semestre | **Ano Letivo:** 2026/1

---

## 🚀 O Desafio: Controle de Saldos Concorrente


O desafio é construir um **Sistema de Controle de Saldos (Crédito e Débito)** capaz de suportar centenas de transações simultâneas sem perder 1 centavo sequer. O problema? Se você não gerenciar a memória e as threads corretamente, o caos financeiro (condições de corrida) vai destruir o seu sistema.

### 🛑 Regras Gerais (Leia com Atenção)
1. **Formação das Equipes:** Os alunos devem formar grupos de até **5 pessoas** para a realização de todo o projeto do bimestre.
2. **Nada de Frameworks Web:** É terminantemente proibido o uso de Spring Boot, Express, ASP.NET Core MVC, Django, etc.
3. **Sem HTTP e JSON:** A comunicação na rede deve ser feita "na unha" utilizando **Sockets TCP**. Os dados devem trafegar através de **Serialização e protocolos binários** (nada de mandar texto puro).
4. **Linguagens Recomendadas:** Java, C#, Go ou Python.
5. **Restrição Node.js:** O uso de Node.js (JavaScript/TypeScript) está **vetado** para a construção do servidor neste 1º bimestre. Como o Node gerencia o *Event Loop* em uma única thread, ele esconde os problemas clássicos de concorrência em memória compartilhada, que são o foco de aprendizado desta etapa.

---

## 📅 Cronograma de Entregas

O projeto será construído de forma incremental e avaliará o seu domínio sobre os conteúdos do bimestre:

### 📦 Entrega 1: A Base da Comunicação (Avaliação Formativa 1)
**Data de Entrega:** 18/03/2026
**Objetivo:** Implementar um Cliente e um Servidor TCP básicos.
* O Servidor deve manter o saldo dos clientes em memória (ex: um Dicionário ou Mapa).
* O Cliente enviará comandos binários contendo: `ID_CLIENTE`, `TIPO_TRANSACAO (C/D)` e `VALOR`.
* O Servidor deve processar as mensagens, atualizar o saldo e responder.
* *Critério de Aceite:* O professor enviará 10 transações sequenciais usando um script próprio. O saldo final deve bater!

### 🚦 Entrega 2: Sobrevivendo ao Caos (Avaliação Formativa 2)
**Data de Entrega:** 09/04/2026
**Objetivo:** Multithreading, Sincronização e Conteinerização.
* O seu servidor agora receberá transações simultâneas. Você deverá implementar **Threads/Processos** e garantir o isolamento da memória usando mecanismos de **Sincronização e exclusão mútua** (Mutex, Locks).
* O servidor deve ser entregue obrigatoriamente rodando dentro de um **Container Docker**. Inclua o `Dockerfile` no repositório.
* *Critério de Aceite:* Teste de estresse com 50 clientes simultâneos. Se o saldo não bater ao final por conta de *race conditions*, a entrega não será validada. O projeto deve rodar com um simples `docker build` e `docker run`.

### ⚔️ Entrega 3: A Rinha Final (Avaliação Bimestral)
**Data de Entrega:** 23/04/2026
**Objetivo:** Orquestração local e gargalo de recursos.
* O sistema deve rodar com **múltiplas réplicas (instâncias)** do seu servidor, balanceadas por um Load Balancer (Nginx, HAProxy, etc.) configurado via Docker Compose.
* O estado (saldos) precisará ser compartilhado entre essas instâncias (pode usar um Redis ou banco de dados leve em outro contêiner).
* **A Maldade:** Seus contêineres de servidor terão limites severos de CPU e Memória configurados no Compose.
* *Critério de Aceite:* A aplicação será bombardeada por um *Stress Tester*. A avaliação considerará a consistência dos dados, a disponibilidade (quantas conexões caíram) e a performance sob recursos limitados.

---

## 💡 Dicas de Ouro

* **Comece Simples:** Faça a comunicação cliente-servidor funcionar com 1 cliente enviando 1 byte antes de tentar enviar estruturas complexas.
* **Cuidado com Deadlocks:** Ao usar Locks ou Mutex, garanta que você sempre vai liberá-los, mesmo que ocorra um erro na transação.
* **Estude Serialização:** Converter inteiros e decimais para arrays de bytes e vice-versa é a chave da Entrega 1.
* **Teste sua API localmente:** Não espere o dia da entrega para descobrir que seu servidor "quebra" quando duas pessoas enviam comandos no mesmo milissegundo.

---

## 🛠️ Como Submeter
1. Faça um Fork/Clone deste repositório.
2. Crie uma pasta com o nome e RA dos integrantes do grupo (ex: `Grupo_Joao123_Maria456_Pedro789`).
3. Façam os commits regularmente, evidenciando o trabalho em equipe.
4. Para cada entrega, crie uma Tag no Git (ex: `v1.0-formativa1`) ou faça o push até às 23h59 da data estipulada.
5. As instruções de como rodar o seu projeto (comandos Docker) devem estar rigorosamente documentadas no README do seu grupo.

Boa sorte e que a concorrência esteja a favor do seu grupo! 🚀