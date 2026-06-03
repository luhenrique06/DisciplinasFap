
Bem-vindos ao desafio prático do 1º Bimestre da disciplina de **Sistemas Distribuídos e Computação em Nuvem** do curso de **Sistemas de Informação** da **Faculdade de Apucarana (FAP)**.

**Professor:** Dr. Luiz Henrique Custódio Mendes Marques
**Semestre:** 7º Semestre | **Ano Letivo:** 2026/1


### Avaliação bimestral- Prova pratica desenvolvida em aula
**Data:** 23/06/2026
Exercitar, na prática, conceitos fundamentais de **sistemas distribuídos** e **computação em nuvem**: provisionamento de infraestrutura, conteinerização, exposição de serviços em rede pública e resolução de nomes via DNS. Ao final, cada aluno (ou grupo) deve ter um sistema rodando em um provedor de nuvem, **acessível pela internet por meio de um nome de domínio**.

## Descrição da atividade

Você deverá disponibilizar um sistema (uma aplicação web simples, uma API REST ou um sistema desenvolvido em outra disciplina/projeto pessoal) em um provedor de nuvem pública. O sistema deve estar **conteinerizado com Docker** e **exposto à internet** sob um nome de domínio configurado via **CNAME**.

Escolha **um** dos provedores, todos com camada gratuita (*free tier*):

- **AWS** (EC2)
- **Azure** (Virtual Machines)
- **Oracle Cloud** (Compute Instances)

## Requisitos técnicos (etapas obrigatórias)

1. **Provisionar uma máquina virtual** em um dos provedores. Use uma instância do *free tier*:
   - AWS: `t2.micro` / `t3.micro`
   - Azure: `B1s`
   - Oracle: `VM.Standard.E2.1.Micro` ou Ampere A1
2. **Instalar o Docker** na máquina (`docker` + `docker compose`). A entrega deve evidenciar a instalação via terminal.
3. **Subir o sistema** em container(s). Recomenda-se um `Dockerfile` próprio e/ou um `docker-compose.yml` quando houver mais de um serviço (ex.: aplicação + banco de dados).
4. **Expor o sistema na internet**, liberando a porta adequada no *firewall* / *security group* do provedor (ex.: 80/443) e validando o acesso pelo IP público.
5. **Configurar um CNAME** apontando um domínio (gratuito) para o endereço da sua aplicação na nuvem, de modo que o sistema seja acessível por um nome amigável em vez do IP. Dica, pode ser o NGROK -> instalar na maquina da cloud e subir o dominio free



### GitHub Student Developer Pack (domínio "real" grátis)

O pacote de estudante do GitHub inclui um **domínio `.me` gratuito por 1 ano** (via Namecheap). Combinado com o **Cloudflare** (DNS gratuito), dá controle total de CNAME, A e SSL. É o melhor caminho para quem quer um domínio de verdade.


