# Roteiro de Entrevistas - Projeto GAC

Este documento centraliza as perguntas essenciais para a fase de levantamento de requisitos junto aos *stakeholders* do projeto. O objetivo é validar premissas financeiras, operacionais, legais e técnicas.

## 1. Perguntas Gerais: Viabilidade e Custos

*Essas perguntas serão feitas para os entrevistados!*

* Qual o custo total você acha que esse projeto pode ter?
* Você acha que esse investimento trará retorno?
* Sobre esse retorno, você pensou sobre manutenções e o suporte por parte dos desenvolvedores?
* Isso entrou na sua lista de custos?
* Pensando no trabalho, nas dificuldades e no conhecimento necessário para criar e gerenciar a aplicação, você acha um valor justo?
* Esse valor que você pensou, você acha que uma equipe inteira é suprida com ele?
* Você acha que o custo só quem paga é o cliente?
* Ou você acha que os desenvolvedores podem acabar arcando com algum custo, seja em dinheiro ou tempo, levando em conta uma requisição feita de forma incorreta por parte do cliente?

---

## 2. Perguntas Específicas por Stakeholder

Para garantir que o sistema atenda à *Visão da Demanda*, as perguntas abaixo devem ser direcionadas aos atores específicos da rotina do CCT.

### 2.1. Diretoria do CCT (Foco: Estratégia e ROI)

* Atualmente, qual é a estimativa de prejuízo financeiro anual por perda, quebra ou extravio de ativos (projetores, cabos, etc.)?
* Qual é o orçamento disponível para a aquisição da infraestrutura física inicial (Tags NFC, QR Codes e eventuais tablets/smartphones para o balcão)?
* Quais métricas institucionais a Diretoria usará para considerar este projeto um sucesso em seus primeiros 6 meses?

### 2.2. Coordenação / Admin (Foco: Regras de Negócio e Gestão)

* Qual é o volume diário/semanal de empréstimos e devoluções no setor?
* Quanto tempo a equipe administrativa gasta hoje apenas processando, armazenando e auditando os formulários de papel?
* Como funciona a regra de bloqueio de um professor caso ele danifique um equipamento? O sistema deve automatizar esse bloqueio?
* Como vocês gostariam de visualizar os relatórios e *dashboards* de uso? (ex: por bloco, por turno, por professor, taxa de depreciação).

### 2.3. Setor de Patrimônio (Foco: Integração e Cadastro)

* Como os equipamentos chegam ao CCT hoje? Existe um sistema legado da Unifor de onde precisaremos importar dados (via API ou planilhas)?
* O número de patrimônio existente hoje segue um padrão fixo (ex: apenas números, quantidade exata de dígitos)?
* Como o sistema deve lidar com a "baixa" de um equipamento que atingiu o fim de sua vida útil?

### 2.4. Atendentes / Secretaria (Foco: Operação e Checklists)

* No momento de maior pico de troca de turnos, quanto tempo vocês têm, em média, para atender cada professor?
* Quais são as avarias ou faltas mais comuns (ex: falta de cabo USB, lente riscada) que acabam passando despercebidas no formulário de papel?
* A conferência visual guiada por um checklist no aplicativo do balcão pode atrasar a fila? Como podemos otimizar essa tela?
* Com que frequência ocorre a passagem não oficial de equipamentos entre professores sem passar pelo balcão?

### 2.5. Professores Solicitantes (Foco: Usabilidade / Fricção Zero)

* O que mais incomoda você no processo atual de empréstimo de chaves e projetores?
* Se a assinatura em papel for substituída por um toque do seu crachá (ou celular) com um clique de "Aceito a Responsabilidade" no app, isso facilitaria sua rotina?
* Você costuma repassar o equipamento para o professor do horário seguinte? Se houvesse uma forma no aplicativo de transferir essa carga oficialmente em 10 segundos, você utilizaria?

### 2.6. Jurídico Institucional (Foco: Compliance e Legalidade)

* Quais são os requisitos legais mínimos para que o "Termo de Responsabilidade Eletrônico" assinado via aplicativo tenha validade para cobranças financeiras em caso de danos?
* Precisamos de integração com o sistema de autenticação único (SSO/Login) da Unifor para garantir a identidade de quem está locando?
* Como devem ser armazenados os *logs* de transação (timestamps) para servirem como prova em caso de contestação pelo usuário?
