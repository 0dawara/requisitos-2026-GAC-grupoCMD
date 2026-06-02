# Especificação de Regras de Negócio (RN) - Projeto GAC

Este documento descreve as regras que regem os processos de gestão de ativos do CCT, garantindo a integridade dos dados e a conformidade com as diretrizes institucionais.

## Histórico de Versões

| Data | Versão | Descrição | Autor |
| :--- | :--- | :--- | :--- |
| 19/05/2026 | 1.0 | Elaboração inicial das regras de negócio do GAC. | Grupo CMD |
| 19/05/2026 | 1.1 | Sincronização de atores com o Documento de Visão (v1.3). | Grupo CMD |

---

## 1. Regras de Locação e Posse

### RN01 - Aceite de Termo de Responsabilidade

* **Identificador:** RN01 - Professor aceita Termo de Responsabilidade Eletrônico.
* **Descrição:** Toda locação de ativo(s) exige que o Professor realize o aceite digital de um Termo de Responsabilidade no momento da confirmação da retirada. Sem o aceite, o sistema impede a vinculação do ativo ao usuário.

### RN02 - Bloqueio de Múltiplas Locações Pendentes

* **Identificador:** RN02 - Sistema restringe locações para usuários inadimplentes.
* **Descrição:** Se um Professor possuir ativos com prazo de devolução expirado, o sistema deve impedir novas solicitações de reserva até que a pendência seja regularizada.

---

## 2. Regras de Transferência

### RN03 - Validação de Transferência via Identificador Físico

* **Identificador:** RN03 - Professores realizam transferência mediante leitura física.
* **Descrição:** A transferência de responsabilidade de um ativo de um Professor (Cedente) para outro (Cessionário) só é efetivada se o Cessionário realizar a leitura física da Tag NFC ou QR Code do equipamento em seu próprio dispositivo mobile.

### RN04 - Notificação Imediata de Transferência

* **Identificador:** RN04 - Sistema notifica partes interessadas sobre transferência.
* **Descrição:** Ao concluir uma transferência direta, o sistema deve enviar notificações automáticas para o Professor Cedente (confirmando a baixa) e para o Atendente de plantão (para ciência da nova localização do ativo).

---

## 3. Regras de Devolução e Integridade

### RN05 - Conferência Obrigatória de Avarias

* **Identificador:** RN05 - Atendente registra estado físico na devolução.
* **Descrição:** Todo processo de devolução exige o preenchimento de um checklist de integridade. Caso existam avarias não registradas previamente, o sistema deve gerar um alerta automático para a **Administrador**.

### RN06 - Baixa Automática de Responsabilidade

* **Identificador:** RN06 - Sistema encerra vínculo após confirmação da devolução.
* **Descrição:** A responsabilidade oficial do Professor sobre o ativo só é encerrada após a confirmação manual do Atendente no sistema, baseada na conferência física do equipamento.

---

## 4. Regras de Inventário

### RN07 - Unicidade de Identificadores Físicos

* **Identificador:** RN07 - Administrador vincula apenas uma Tag NFC/QR Code por patrimônio.
* **Descrição:** O sistema não permite que uma mesma Tag NFC ou QR Code seja vinculada a mais de um número de patrimônio simultaneamente.

### RN08 - Rastreabilidade de Inativação

* **Identificador:** RN08 - Administrador justifica inativação de ativo.
* **Descrição:** Ao inativar um ativo (devido a perda, roubo ou obsolescência), o sistema exige a inserção de uma justificativa textual e o registro da data/hora da ocorrência para fins de auditoria.

---

## 5. Checklist de Validação da Regra de Negócio

Use este checklist antes de finalizar a regra.

### 5.1 Estrutura mínima

* [x] Identificador único e padronizado (ex.: RN1, RN1.1, RN2).
* [x] Nome da regra no formato sujeito + verbo + objeto.
* [x] Descrição clara, direta e sem ambiguidades.

### 5.2 Qualidade da regra

* [x] A regra descreve apenas uma decisão/comportamento principal.
* [x] Condições de aplicação (gatilho/contexto) estão explícitas.
* [x] Resultado esperado da regra está explícito.
* [x] A regra é verificável e testável.

### 5.3 Consistência e rastreabilidade

* [x] Não há conflito com outras regras já existentes.
* [x] A regra referencia origem (negócio, norma, lei ou decisão do cliente), quando aplicável.
* [x] A regra está alinhada com CDU, RNF e demais artefatos relacionados.

### 5.4 Prontidão

* [x] Conteúdo revisado por pares.
* [x] Regra pronta para uso em análise, desenvolvimento e testes.
