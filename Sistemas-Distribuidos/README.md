
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

### 🚦 Entrega 2: Multithreading e docker (Avaliação bimestral)
**Data de Entrega:** 09/04/2026
**Objetivo:** Multithreading, Sincronização e Conteinerização.
* O seu servidor agora receberá transações simultâneas. Você deverá implementar **Threads/Processos** e garantir o isolamento da memória usando mecanismos de **Sincronização e exclusão mútua** (Mutex, Locks).
* O servidor deve ser entregue obrigatoriamente rodando dentro de um **Container Docker**. Inclua o `Dockerfile` no repositório.
* *Critério de Aceite:* Ser resistente a  *race conditions*. O projeto deve rodar com um simples `docker build` e `docker run`.


---