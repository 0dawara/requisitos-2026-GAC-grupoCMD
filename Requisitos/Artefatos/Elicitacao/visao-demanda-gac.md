# Visão da Demanda (VD) - Projeto GAC

## Histórico de Versões

| Data | Versão | Descrição | Autor |
| :--- | :--- | :--- | :--- |
| 04/05/2026 | 1.0 | Criação inicial do Documento de Visão para o projeto GAC. | Grupo CMD |
| 18/05/2026 | 1.1 | Revisão da Visão de Demanda com base no feedback do Product Owner. | Grupo CMD |

## 1. Objetivo

O objetivo principal do Projeto GAC é criar uma plataforma digital integrada a identificadores físicos (como tags NFC e QR Codes) para apoiar e rastrear todo o ciclo de vida dos equipamentos (ativos) do Centro de Ciências e Tecnologia (CCT) da Universidade de Fortaleza (Unifor). A iniciativa visa substituir os métodos de controle manuais por um sistema digital que traga confiabilidade tanto para o inventário quanto para as transações de empréstimo e devolução, garantindo a responsabilização adequada de quem locou o ativo e rastreabilidade de sua movimentação.

## 2. Proposta de Valor

A solução entrega valor ao transformar um controle manual fragmentado entre modelos analógicos (formulário em papel) e digitais manuais (planilhas) em um processo digital automatizado que gera histórico para auditoria e visibilidade em tempo real. A proposta de valor é fundamentada na "Tríade da Rastreabilidade", garantindo:

* **Usabilidade:** O uso de hardware NFC (ou QR Code) e um aplicativo móvel garantem agilidade para que o sistema não atrapalhe a rotina de aulas dos professores.
* **Operação:** A exigência de uma conferência exata no momento da devolução do ativo.
* **Auditoria:** A utilização de um login associado a um Termo de Responsabilidade Eletrônico e o registro de histórico de movimentações garantem a responsabilização e rastreabilidade adequadas.

## 3. Descrição da Demanda

O modelo atual de controle de ativos (projetores e chaves) no CCT baseia-se em formulários de papel (Termos de Saída e Entrada). Isso gera "pontos cegos", como falta de rastreio de transferências entre salas, caligrafias ilegíveis, preenchimento apressado e riscos por dados desatualizados.

A demanda consiste em um sistema digital que permitirá:

* Digitalização do aceite dos Termos de Responsabilidade.
* Transferência oficial de equipamentos diretamente entre professores.
* Vínculo físico-digital seguro para cada equipamento.
* Controle preciso do ciclo de vida de ativos.
* Alertas automáticos para inconsistências operacionais.

## 4. Partes Interessadas

| Nome | Papel | Responsabilidades | Representante |
| :--- | :--- | :--- | :--- |
| **Diretoria do CCT** | Cliente | Segurança e responsabilização institucional do patrimônio. | Diretor do CCT |
| **Professor** | Usuário final | Locar, utilizar e devolver o(s) ativo(s). | Professores CCT |
| **Atendentes** | Usuário chave | Validar movimentações (entrega/devolução) e realizar checklists de avarias. | Secretaria do CCT |
| **Coordenação / Admin.** | Stakeholder | Monitorar o inventário, processos e relatórios operacionais. | Coord. do CCT |
| **Setor de Patrimônio** | Stakeholder | Controle inicial da origem e identificação global da Unifor. | Setor Central |
| **Equipe de TI / Grupo CMD** | Desenvolvimento | Projetar, implementar e manter a segurança e usabilidade da plataforma. | Grupo CMD |
| **Jurídico Institucional** | Stakeholder Consultivo | Validadores da legalidade do Termo de Responsabilidade Eletrônico e assinaturas digitais. | Jurídico Unifor |

## 5. Personas

### 5.1. Professor

* **Descrição:** Docente do CCT que precisa locar projetores, chaves e acessórios para ministrar suas aulas. Possui grande pressão de tempo entre turnos.
* **Objetivo:** Retirar ativos rapidamente, assumindo a responsabilidade oficial sem burocracias demoradas, quando necessário transferir essa responsabilidade para o próximo professor e devolver o(s) ativo(s) no prazo estipulado.

### 5.2. Atendente

* **Descrição:** Funcionário administrativo que interage com os professores para realizar as movimentações de equipamentos.
* **Objetivo:** Validar as movimentações e garantir o registro correto de avarias e a conferência de itens do kit na devolução.

### 5.3. Administrador

* **Descrição:** Responsável pela gestão dos recursos físicos do centro.
* **Objetivo:** Gerenciar o cadastro de ativos (projetores, cabos e chaves) e consultar o histórico de movimentações.

## 6. Necessidades e Funcionalidades

### Necessidade 1: Cadastro de Ativos

#### F1.1 CRUD de Projetores

* **Descrição:** Cadastro, consulta, atualização e exclusão de projetores com seus dados: número de patrimônio, Tag NFC e QR Code.
* **Incluída:** Sim.
* **Atores:** Administrador.
* **Frequência:** Baixa.
* **Valor:** Alto.

#### F1.2 CRUD de Cabos

* **Descrição:** Cadastro, consulta, atualização e exclusão de cabos com seus dados: número de patrimônio, tipo, Tag NFC e QR Code.
* **Incluída:** Sim.
* **Atores:** Administrador.
* **Frequência:** Baixa.
* **Valor:** Alto.

#### F1.3 CRUD de Chaves

* **Descrição:** Cadastro, consulta, atualização e exclusão de chaves com sua respectiva sala, Tag NFC e QR Code.
* **Incluída:** Sim.
* **Atores:** Administrador.
* **Frequência:** Baixa.
* **Valor:** Alto.

#### F1.4 Inativação de Ativos

* **Descrição:** Inativação de projetores, cabos e chaves.
* **Incluída:** Sim.
* **Atores:** Administrador.
* **Frequência:** Baixa.
* **Valor:** Alto.

#### F1.5 Histórico do Cadastro de Ativos

* **Descrição:** Registro do histórico de movimentações do cadastro de projetores, cabos e chaves.
* **Incluída:** Sim.
* **Atores:** Sistema.
* **Frequência:** Média.
* **Valor:** Alto.

### Necessidade 2: Locação Ágil e Segura

#### F2.1 Reserva Ágil de Ativos

* **Descrição:** Solicitação de reserva de ativos feita pelo professor através do sistema, com preenchimento de informações necessárias para a reserva.
* **Incluída:** Sim.
* **Atores:** Professor.
* **Frequência:** Alta.
* **Valor:** Alto.

#### F2.2 Confirmação de Locação

* **Descrição:** Confirmação de locação feita pelo atendente através do sistema, com conferência de todos os itens do kit e aprovação da locação na retirada.
* **Incluída:** Sim.
* **Atores:** Atendente.
* **Frequência:** Alta.
* **Valor:** Alto.

#### F2.3 Transferência de Ativos entre Professores

* **Descrição:** Permite a transferência de ativos de um professor para outro no sistema, mantendo a rastreabilidade, através da leitura dos QR Codes ou Tags NFC.
* **Incluída:** Sim.
* **Atores:** Professor.
* **Frequência:** Baixa.
* **Valor:** Alto.

#### F2.4 Histórico de Locação de Ativos

* **Descrição:** Registro do histórico de locação de ativos.
* **Incluída:** Sim.
* **Atores:** Sistema.
* **Frequência:** Alta.
* **Valor:** Alto.

### Necessidade 3: Devolução de Ativos

#### F3.1 Devolução de Ativos

* **Descrição:** Permite o registro de devolução do(s) ativo(s) pelo atendente após a conferência do(s) mesmo(s).
* **Incluída:** Sim.
* **Atores:** Atendente.
* **Frequência:** Alta.
* **Valor:** Alto.

#### F3.2 Histórico de Devolução de Ativos

* **Descrição:** Registro do histórico de devolução de ativos.
* **Incluída:** Sim.
* **Atores:** Sistema.
* **Frequência:** Alta.
* **Valor:** Alto.

### Necessidade 4: Notificações e Monitoramento

#### F4.1 Alertas e Notificações

* **Descrição:** Geração de lembretes sobre atrasos de devolução e notificações de transferência para os atores vinculados ao(s) ativo(s).
* **Incluída:** Sim.
* **Atores:** Atendente e Professor.
* **Frequência:** Média.
* **Valor:** Alto.

## 7. Arquitetura da Demanda

A plataforma GAC baseia-se num ecossistema composto por 4 camadas principais:

### 1. Identificadores Físicos

* Tags NFC
* QR Codes

### 2. Frontend Mobile

* Acesso via smartphone (Android ou iOS)
* Acesso para ambos usuários
* Solicitação de locação
* Devolução de ativos
* Transferência de ativos
* Histórico de locação de ativos
* Alertas e notificações
* Histórico de devolução de ativos
* Histórico do cadastro de ativos

### 3. Frontend Web

* Acesso via navegador web
* Cadastro de ativos
* Inativação de ativos
* Histórico do cadastro de ativos
* Confirmação de locação
* Devolução de ativos
* Alertas e notificações
* Histórico de devolução de ativos
* Histórico de locação de ativos

### 4. Backend

* Módulo de autenticação
* Módulo de gerenciamento de usuários
* Módulo de cadastro de ativos
* Módulo de locação de ativos
* Módulo de devolução de ativos
* Módulo de transferência de ativos
* Módulo de alertas e notificações

---

## Checklist de Validação do Documento de Visão

* [x] O objetivo está claro e alinhado ao problema/necessidade?
* [x] A proposta de valor é mensurável e relevante?
* [x] Todas as partes interessadas estão listadas com papéis definidos?
* [x] Existem pelo menos duas personas descritas?
* [x] Todas as necessidades e funcionalidades estão relacionadas a atores?
* [x] Há indicação de valor e frequência para cada funcionalidade?
* [x] A arquitetura está ilustrada (mesmo que de forma simples)?
* [x] O documento está escrito em linguagem clara e objetiva?
