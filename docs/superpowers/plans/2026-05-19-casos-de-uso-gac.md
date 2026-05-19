# GAC Use Cases Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Generate 1 Mermaid diagram and 6 detailed Markdown use case specifications based on the LAPIS template and GAC functional requirements.

**Architecture:** Granular file structure. Diagrams in `Requisitos/Artefatos/Diagramas/` and specifications in `Requisitos/Artefatos/CasosDeUso/`.

**Tech Stack:** Markdown, Mermaid.

---

### Task 1: Create Mermaid Diagram

**Files:**
- Create: `Requisitos/Artefatos/Diagramas/cdu-gac-geral.mmd`

- [ ] **Step 1: Write the diagram content**

```mermaid
useCaseDiagram
    actor "Professor" as P
    actor "Atendente" as AT
    actor "Administrador" as AD
    
    package "GAC - Gestão de Ativos do CCT" {
        usecase "CDU-01: Solicitar Reserva" as UC1
        usecase "CDU-02: Confirmar Locação" as UC2
        usecase "CDU-03: Transferir Ativo" as UC3
        usecase "CDU-04: Registrar Devolução" as UC4
        usecase "CDU-05: Gerenciar Ativos" as UC5
        usecase "CDU-06: Auditar Movimentações" as UC6
    }
    
    P --> UC1
    P --> UC3
    AT --> UC2
    AT --> UC4
    AD --> UC5
    AD --> UC6
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/Diagramas/cdu-gac-geral.mmd
git commit -m "docs: create general use case diagram"
```

---

### Task 2: Create CDU-01 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-01-solicitar-reserva.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                  | Autor         |
| ---------- | ------- | -------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-01 - Solicitar Reserva | Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-01 - Solicitar Reserva

## 2. Objetivo

Permitir que o Professor solicite a reserva de ativos (projetores, cabos, chaves) para um determinado horário e sala.

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Professor

### 4.2 Secundário
Não se aplica

## 5. Precondições

* O Professor deve estar logado no sistema.
* O Professor não pode possuir pendências de devolução (bloqueio de inadimplentes).

## 6. Fluxo Principal

### P1. O Professor seleciona a opção "Nova Reserva".
### P2. O sistema apresenta o formulário com data, horário e sala.
### P3. O Professor preenche os dados e solicita a busca de ativos disponíveis.
### P4. O sistema lista os ativos disponíveis (projetores, chaves, cabos) para o período.
### P5. O Professor seleciona os ativos desejados e clica em "Confirmar Reserva".
### P6. O sistema valida os dados, registra a reserva com status "Aguardando Retirada" e exibe mensagem de sucesso.
### P7. O caso de uso é encerrado.

## 7. Fluxos Alternativos

### A1. Cancelamento da Reserva
#### A1.1 No passo P5, o Professor seleciona a opção "Cancelar".
#### A1.2 O sistema descarta as seleções e retorna à tela inicial. O caso de uso é encerrado.

## 8. Fluxos de Exceção

### E1. Professor com Pendências
#### E1.1 No passo P1, o sistema identifica que o Professor possui devoluções em atraso.
#### E1.2 O sistema exibe mensagem informando a pendência e bloqueia a nova reserva. O caso de uso é encerrado.

### E2. Nenhum Ativo Disponível
#### E2.1 No passo P4, o sistema não encontra ativos disponíveis para o período informado.
#### E2.2 O sistema exibe mensagem "Nenhum ativo disponível" e permite que o Professor altere o horário ou data (retorna ao passo P2).

## 9. Pós-condições

Uma nova reserva é criada no sistema e vinculada ao Professor, aguardando a confirmação de retirada.

## 10. Requisitos Não Funcionais

Não se aplica.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Alta.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F2.1)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-01-solicitar-reserva.md
git commit -m "docs: add CDU-01 Solicitar Reserva"
```

---

### Task 3: Create CDU-02 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-02-confirmar-locacao.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                  | Autor         |
| ---------- | ------- | -------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-02 - Confirmar Locação | Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-02 - Confirmar Locação

## 2. Objetivo

Permitir que o Atendente confirme a entrega física dos ativos reservados ao Professor e registre o aceite do Termo de Responsabilidade.

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Atendente

### 4.2 Secundário
Professor

## 5. Precondições

* O Atendente deve estar logado no sistema.
* Deve existir uma reserva com status "Aguardando Retirada".

## 6. Fluxo Principal

### P1. O Atendente seleciona a reserva do Professor no sistema.
### P2. O sistema exibe os detalhes da reserva e os ativos solicitados.
### P3. O Atendente realiza a conferência dos itens e escaneia o identificador físico (NFC/QR Code) de cada ativo.
### P4. O sistema valida os ativos lidos com os reservados.
### P5. O sistema solicita o aceite digital do Termo de Responsabilidade ao Professor.
### P6. O Professor confirma o aceite digital pelo aplicativo ou assinatura no balcão.
### P7. O sistema registra a locação, transfere a responsabilidade para o Professor e atualiza o status do ativo para "Em Uso".
### P8. O caso de uso é encerrado.

## 7. Fluxos Alternativos

### A1. Locação Expressa (Sem Reserva Prévia)
#### A1.1 No passo P1, o Atendente seleciona "Nova Locação Direta".
#### A1.2 O Atendente seleciona o Professor e escaneia os ativos.
#### A1.3 O sistema segue para o passo P5.

## 8. Fluxos de Exceção

### E1. Ativo Incorreto ou Com Defeito
#### E1.1 No passo P4, o sistema acusa erro na leitura do ativo ou o Atendente nota um defeito.
#### E1.2 O Atendente substitui o ativo físico, escaneia o novo e o sistema atualiza a reserva (retorna ao passo P3).

### E2. Professor Recusa o Termo
#### E2.1 No passo P6, o Professor recusa o aceite do termo.
#### E2.2 O sistema cancela o processo de locação e os ativos não são entregues. O caso de uso é encerrado.

## 9. Pós-condições

O ativo é registrado como "Em Uso" e o Professor passa a ser o responsável físico pelo equipamento.

## 10. Requisitos Não Funcionais

Não se aplica.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Alta.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F2.2)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-02-confirmar-locacao.md
git commit -m "docs: add CDU-02 Confirmar Locacao"
```

---

### Task 4: Create CDU-03 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-03-transferir-ativo.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                  | Autor         |
| ---------- | ------- | -------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-03 - Transferir Ativo  | Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-03 - Transferir Ativo

## 2. Objetivo

Permitir a transferência direta da responsabilidade de um ativo de um Professor (Cedente) para outro Professor (Cessionário).

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Professor (Cedente)

### 4.2 Secundário
Professor (Cessionário)

## 5. Precondições

* Ambos os Professores devem possuir o aplicativo móvel com sessão ativa.
* O Professor Cedente deve ser o atual responsável pelo ativo.
* O Professor Cessionário não pode ter pendências ativas.

## 6. Fluxo Principal

### P1. O Professor Cedente acessa o aplicativo e seleciona "Transferir Ativo".
### P2. O sistema lista os ativos sob responsabilidade do Cedente.
### P3. O Professor Cedente seleciona o ativo e confirma a intenção de transferência.
### P4. O sistema gera um QR Code (ou aguarda aproximação NFC) no dispositivo do Cedente.
### P5. O Professor Cessionário abre seu aplicativo, seleciona "Receber Transferência" e escaneia o ativo/dispositivo do Cedente.
### P6. O sistema exibe o Termo de Responsabilidade para o Cessionário.
### P7. O Professor Cessionário aceita o termo.
### P8. O sistema encerra a responsabilidade do Cedente, transfere para o Cessionário e envia notificação de sucesso.
### P9. O caso de uso é encerrado.

## 7. Fluxos Alternativos

Não se aplica.

## 8. Fluxos de Exceção

### E1. Cessionário com Pendências
#### E1.1 No passo P5, após o escaneamento, o sistema identifica que o Cessionário possui devoluções em atraso.
#### E1.2 O sistema exibe mensagem de erro e bloqueia a transferência. O caso de uso é encerrado.

### E2. Tempo Limite Excedido
#### E2.1 No passo P4, o Cessionário demora muito para escanear.
#### E2.2 O sistema expira a solicitação e solicita que o Cedente inicie novamente (retorna ao passo P1).

## 9. Pós-condições

A responsabilidade pelo ativo é transferida oficialmente e o histórico de movimentação é registrado.

## 10. Requisitos Não Funcionais

* **Sincronização Offline:** O sistema deve suportar este fluxo offline e sincronizar assim que a conexão for reestabelecida.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Baixa.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F2.3)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-03-transferir-ativo.md
git commit -m "docs: add CDU-03 Transferir Ativo"
```

---

### Task 5: Create CDU-04 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-04-registrar-devolucao.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                    | Autor         |
| ---------- | ------- | ---------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-04 - Registrar Devolução| Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-04 - Registrar Devolução

## 2. Objetivo

Permitir que o Atendente registre o retorno de um ativo, finalize a responsabilidade do Professor e verifique a integridade do equipamento.

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Atendente

### 4.2 Secundário
Professor

## 5. Precondições

* O Atendente deve estar logado no sistema.
* O ativo deve estar com o status "Em Uso".

## 6. Fluxo Principal

### P1. O Atendente seleciona a opção "Registrar Devolução" e escaneia o identificador físico (NFC/QR Code) do ativo.
### P2. O sistema localiza o ativo e exibe os dados do Professor responsável e os itens associados.
### P3. O Atendente inspeciona o ativo e preenche o checklist de integridade (cabos, funcionamento, avarias).
### P4. O Atendente assinala que o ativo está em perfeitas condições e clica em "Confirmar Devolução".
### P5. O sistema atualiza o status do ativo para "Disponível", encerra a responsabilidade do Professor e registra a movimentação.
### P6. O caso de uso é encerrado.

## 7. Fluxos Alternativos

Não se aplica.

## 8. Fluxos de Exceção

### E1. Identificação de Avaria
#### E1.1 No passo P3, o Atendente identifica uma avaria ou falta de componente.
#### E1.2 O Atendente assinala a avaria no checklist e preenche a observação.
#### E1.3 O sistema registra a devolução com ressalvas, altera o status do ativo para "Em Manutenção" e gera um alerta para o Administrador.
#### E1.4 O caso de uso segue para o encerramento.

### E2. Leitura Falha do Identificador
#### E2.1 No passo P1, o identificador NFC/QR Code está danificado.
#### E2.2 O Atendente digita manualmente o código patrimonial. O sistema segue para o passo P2.

## 9. Pós-condições

O vínculo do Professor com o ativo é encerrado. O ativo volta a ficar "Disponível" ou entra "Em Manutenção".

## 10. Requisitos Não Funcionais

Não se aplica.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Alta.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F3.1)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-04-registrar-devolucao.md
git commit -m "docs: add CDU-04 Registrar Devolucao"
```

---

### Task 6: Create CDU-05 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-05-gerenciar-ativos.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                  | Autor         |
| ---------- | ------- | -------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-05 - Gerenciar Ativos  | Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-05 - Gerenciar Ativos

## 2. Objetivo

Permitir que o Administrador mantenha o cadastro dos ativos do CCT (cadastrar, alterar, consultar e inativar).

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Administrador

### 4.2 Secundário
Não se aplica

## 5. Precondições

* O Administrador deve estar logado no sistema com perfil adequado.

## 6. Fluxo Principal (Cadastrar Ativo)

### P1. O Administrador seleciona a opção "Gerenciar Ativos" e clica em "Novo Ativo".
### P2. O sistema exibe um formulário de cadastro.
### P3. O Administrador preenche os dados: Número de patrimônio, Tipo de Ativo (Projetor, Cabo, Chave) e cadastra o Identificador Físico (Tag NFC/QR).
### P4. O Administrador clica em "Salvar".
### P5. O sistema valida a unicidade do identificador e do patrimônio.
### P6. O sistema grava o ativo e exibe mensagem de sucesso.
### P7. O caso de uso é encerrado.

## 7. Fluxos Alternativos

### A1. Inativar Ativo
#### A1.1 No passo P1, o Administrador busca um ativo existente e clica em "Inativar".
#### A1.2 O sistema solicita o preenchimento de uma justificativa (extravio, dano permanente, baixa).
#### A1.3 O Administrador preenche e confirma.
#### A1.4 O sistema inativa o ativo, registrando data, hora e justificativa. O caso de uso é encerrado.

### A2. Alterar Ativo
#### A2.1 No passo P1, o Administrador busca um ativo e clica em "Editar".
#### A2.2 O sistema exibe os dados para alteração.
#### A2.3 O Administrador altera os dados e salva. O sistema valida e atualiza os registros (vai para P5).

## 8. Fluxos de Exceção

### E1. Patrimônio ou Identificador Duplicado
#### E1.1 No passo P5, o sistema identifica que o Número de Patrimônio ou Identificador Físico já está em uso por outro ativo ativo.
#### E1.2 O sistema exibe mensagem de erro e solicita correção. Retorna ao passo P3.

## 9. Pós-condições

O inventário de ativos do sistema é atualizado.

## 10. Requisitos Não Funcionais

Não se aplica.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Baixa.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F1.1 a F1.4)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-05-gerenciar-ativos.md
git commit -m "docs: add CDU-05 Gerenciar Ativos"
```

---

### Task 7: Create CDU-06 Specification

**Files:**
- Create: `Requisitos/Artefatos/CasosDeUso/cdu-06-auditar-movimentacoes.md`

- [ ] **Step 1: Write the specification content**

```markdown
# Especificação de Requisitos Funcionais

## Caso de Uso (CDU) - LAPIS

## Histórico de Versões

| Data       | Versão | Descrição                                    | Autor         |
| ---------- | ------- | ---------------------------------------------- | ------------- |
| 19/05/2026 | 1.0     | Criação inicial do CDU-06 - Auditar Movimentações | Grupo CMD     |

## 1. Nome do Caso de Uso

CDU-06 - Auditar Movimentações

## 2. Objetivo

Permitir que o Administrador consulte o log completo de movimentações de um ativo ou usuário para fins de auditoria e responsabilização.

## 3. Tipo de Caso de Uso

Concreto

## 4. Atores

### 4.1 Primário
Administrador

### 4.2 Secundário
Não se aplica

## 5. Precondições

* O Administrador deve estar logado no sistema com perfil adequado.

## 6. Fluxo Principal

### P1. O Administrador seleciona a opção "Auditoria" ou "Relatórios de Movimentação".
### P2. O sistema exibe a interface de busca com filtros (Ativo, Professor, Período).
### P3. O Administrador informa o código de um ativo ou nome de um Professor e clica em "Buscar".
### P4. O sistema processa a consulta e exibe a lista cronológica das movimentações (quando locou, transferiu, devolveu e condição física no checklist).
### P5. O Administrador visualiza os dados e, opcionalmente, clica em "Exportar Relatório".
### P6. O caso de uso é encerrado.

## 7. Fluxos Alternativos

Não se aplica.

## 8. Fluxos de Exceção

### E1. Nenhum Registro Encontrado
#### E1.1 No passo P4, o sistema não encontra movimentações para os filtros informados.
#### E1.2 O sistema exibe a mensagem "Nenhum resultado encontrado" e permite nova pesquisa. Retorna ao passo P2.

## 9. Pós-condições

Nenhuma modificação nos dados. Relatório gerado/visualizado.

## 10. Requisitos Não Funcionais

Não se aplica.

## 11. Ponto de Extensão

Não se aplica.

## 12. Frequência de Utilização

Média.

## 13. Interface Visual

Não se aplica.

## 14. Observações

Não se aplica.

## 15. Referências

* Documento de Visão da Demanda (VD F1.5, F2.4, F3.2)
```

- [ ] **Step 2: Commit**

```bash
git add Requisitos/Artefatos/CasosDeUso/cdu-06-auditar-movimentacoes.md
git commit -m "docs: add CDU-06 Auditar Movimentacoes"
```

---
