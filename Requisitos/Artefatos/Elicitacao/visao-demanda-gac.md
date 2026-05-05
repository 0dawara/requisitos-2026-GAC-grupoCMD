# Visão da Demanda (VD) - Projeto GAC

## Histórico de Versões

| Data | Versão | Descrição | Autor |
| --- | --- | --- | --- |
| 04/05/2026 | 1.0 | Criação inicial do Documento de Visão para o projeto GAC | Grupo CMD |

## 1. Objetivo

O objetivo principal do Projeto GAC é criar uma plataforma digital integrada a identificadores físicos (como NFC e/ou QR Code), para apoiar e rastrear todo o ciclo de vida dos equipamentos e ativos do Centro de Ciências e Tecnologia (CCT) da Unifor. A iniciativa visa substituir os métodos de controle manuais por um sistema digital que traga confiabilidade tanto para o inventário quanto para as transações de empréstimo e devolução, garantindo a responsabilização adequada de quem locou o ativo.

## 2. Proposta de Valor

A solução entrega valor ao transformar um controle manual fragmentado em um processo centralizado que gera histórico para auditoria e visibilidade em tempo real. A proposta de valor é fundamentada na "Tríade da Rastreabilidade", garantindo:

* **Fricção Zero (Usabilidade):** O uso de hardware NFC e um aplicativo rápido garantem agilidade para que o sistema não atrapalhe a rotina de aulas dos professores.
* **Rigor Processual (Operação):** A exigência de checklists dinâmicos força uma conferência exata no momento da devolução do ativo.
* **Segurança Institucional (Auditoria):** A utilização de um login associado a um Termo de Responsabilidade Eletrônico cria uma responsabilização inquestionável sobre o manuseio e devolução dos equipamentos.

## 3. Descrição da Demanda

O modelo atual de controle de ativos (como projetores e chaves) no CCT baseia-se em formulários de papel (Termos de Saída e Entrada). Isso gera "pontos cegos", como falta de rastreio de transferências entre salas, caligrafias ilegíveis, preenchimento apressado e riscos patrimoniais por dados desatualizados.

A demanda consiste em um sistema digital que permitirá:
* Digitalização do aceite dos Termos de Responsabilidade.
* Transferência oficial de equipamentos diretamente entre professores.
* Vínculo físico-digital seguro para cada equipamento.
* Controle unificado de kits (ex: projetor + bolsa + cabos).
* Alertas automáticos para atrasos e manutenções preventivas.

## 4. Partes Interessadas

| Nome                 | Papel           | Responsabilidades                   | Representante    |
| -------------------- | --------------- | ----------------------------------- | ---------------- |
| Diretoria do CCT     | Cliente         | Segurança e responsabilização institucional do patrimônio | Diretor do CCT |
| Professor Solicitante| Usuário final   | Locar, utilizar com cuidado e devolver (ou transferir carga) dos ativos | Professores CCT |
| Atendentes (Setor J2)| Usuário chave   | Registrar movimentações (entrega/devolução) e validar checklists de avarias | Kildery, Adail, etc. |
| Coordenação / Admin. | Stakeholder     | Monitorar o inventário, processos e relatórios operacionais | Coord. do CCT |
| Setor de Patrimônio  | Stakeholder     | Controle inicial da origem e identificação global da Unifor | Setor Central |
| Equipe e Sistemas TI | Desenvolvimento | Projetar, implementar e manter a segurança e usabilidade da plataforma | Grupo CMD |

## 5. Personas

### 5.1. Professor Solicitante

- **Descrição:** Docente do CCT que precisa locar projetores, chaves e acessórios para ministrar suas aulas. Possui grande pressão de tempo entre turnos.
* **Objetivo:** Retirar ativos rapidamente, assumindo a responsabilidade oficial sem burocracias demoradas, e (quando necessário) transferir essa responsabilidade para o próximo professor.

### 5.2. Atendente Validador

- **Descrição:** Funcionário administrativo do suporte (ex: Setor J2) que interage balcão-a-balcão.
* **Objetivo:** Registrar as movimentações sem anotações paralelas de papel e garantir, de forma guiada por checklists, o registro correto de avarias e a conferência de itens do kit na devolução.

### 5.3. Administrador do Inventário

- **Descrição:** Coordenação encarregada pela gestão dos recursos físicos do centro.
* **Objetivo:** Manter a base central de dados 100% confiável, visualizar status atual de qualquer ativo e extrair relatórios para tomadas de decisão e auditoria de sinistros.

## 6. Necessidades e Funcionalidades

### Necessidade 1: Rastreabilidade e Cadastro Base

#### F1.1 Vínculo Físico-Digital (Cadastro de Ativos)

- **Descrição:** Cadastro de equipamentos, acessórios e kits associados a Tags NFC ou QR Codes. Define também vida útil estimada.
* **Incluída:** Sim
* **Atores:** Administrador do Inventário, Atendente Validador
* **Frequência:** Baixa (somente inclusão/alteração no inventário)
* **Valor:** Alto

### Necessidade 2: Locação Ágil e Segura

#### F2.1 Retirada Ágil via Mobile (Termo Eletrônico)

- **Descrição:** Autenticação rápida com identificação do usuário e aceite formal de um Termo de Responsabilidade Eletrônico, com registro de timestamp exato e local.
* **Incluída:** Sim
* **Atores:** Professor Solicitante, Atendente Validador
* **Frequência:** Alta
* **Valor:** Alto

#### F2.2 Transferência de Carga Oficial

- **Descrição:** Permite a transferência de responsabilidade de um professor para outro no sistema, mantendo a trilha de rastreabilidade sem que o item precise voltar ao balcão de atendimento.
* **Incluída:** Sim
* **Atores:** Professor Solicitante
* **Frequência:** Média
* **Valor:** Alto

### Necessidade 3: Integridade Física e Devoluções

#### F3.1 Devolução com Checklist Técnico

- **Descrição:** Tela de conferência guiada para auditar a integridade física, presença de todos os itens do kit (ex: projetor, cabos) e funcionamento. Gera registros automáticos de avaria ou perda vinculados à locação.
* **Incluída:** Sim
* **Atores:** Atendente Validador
* **Frequência:** Alta
* **Valor:** Alto

### Necessidade 4: Gestão do Ciclo de Vida e Auditoria

#### F4.1 Alertas e Notificações Preventivas

- **Descrição:** Lembretes sobre atrasos de devolução, alertas operacionais para manutenção preventiva (baseada no ciclo de vida) e notificações de transferência.
* **Incluída:** Sim
* **Atores:** Administrador do Inventário, Professor Solicitante
* **Frequência:** Média
* **Valor:** Médio

#### F4.2 Dashboard Administrativo e Relatórios

- **Descrição:** Painel imutável contendo o histórico de responsáveis, incidentes e visão consolidada de uso de inventário para facilitar auditorias patrimoniais.
* **Incluída:** Sim
* **Atores:** Administrador do Inventário
* **Frequência:** Média
* **Valor:** Alto

## 7. Arquitetura da Demanda

A plataforma GAC baseia-se num ecossistema interligado composto por:

1. **Identificadores Físicos:** Tags NFC ou QR Codes colados aos ativos físicos (projetores, bolsas, cabos, chaves).
2. **Aplicativo Mobile (Front-end 1):** Utilizado para leitura rápida das tags no momento de empréstimo (fricção zero) e devolução com checklists.
3. **Painel/Dashboard Web (Front-end 2):** Interface focada para a administração (cadastro de equipamentos, monitoramento e relatórios).
4. **Backend Centralizado:** API que valida autenticações, processa os Termos Eletrônicos (gerando timestamps confiáveis) e sincroniza a base de dados dos ativos em tempo real para toda a universidade.

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
