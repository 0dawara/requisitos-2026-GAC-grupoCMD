# Especificação de Requisitos Funcionais (RF) - Projeto GAC

> **Sistema de Gestão de Ativos do CCT (GAC)**
>
> Este documento detalha as funcionalidades da plataforma GAC, descrevendo o comportamento esperado do sistema para atender às necessidades de controle de ativos da Unifor.

## Histórico de Versões

| Data | Versão | Descrição | Autor |
| :--- | :--- | :--- | :--- |
| 17/05/2026 | 1.0 | Elaboração inicial dos requisitos funcionais baseada na Visão da Demanda e RNs. | Grupo CMD |

---

## 1. Gestão de Inventário (Necessidade 1)

### RF01 - Manter Cadastro de Ativos

* **Descrição:** O sistema deve permitir que o **Administrador** realize a manutenção (cadastrar, consultar, alterar) de Projetores, Cabos e Chaves.
* **Campos Obrigatórios:** Número de patrimônio, Tipo de Ativo, Identificador Físico (NFC/QR Code) e Status.
* **Regras Relacionadas:** RN07 (Unicidade de Identificadores).
* **Origem:** VD F1.1, F1.2, F1.3.

### RF02 - Inativar Ativo

* **Descrição:** O sistema deve permitir a inativação de ativos que não estejam em uso (extravio, manutenção ou baixa definitiva).
* **Requisito de Fluxo:** Exigir justificativa textual e registrar data/hora.
* **Regras Relacionadas:** RN08 (Justificativa de Inativação).
* **Origem:** VD F1.4.

### RF03 - Consultar Histórico de Alterações de Cadastro

* **Descrição:** O sistema deve disponibilizar ao **Administrador** um log de todas as alterações realizadas nos dados cadastrais dos ativos para fins de auditoria.
* **Origem:** VD F1.5.

---

## 2. Operação de Locação e Posse (Necessidade 2)

### RF04 - Solicitar Reserva de Ativos

* **Descrição:** O sistema deve permitir que o **Professor** selecione ativos disponíveis e solicite uma reserva para um determinado horário/sala.
* **Restrição:** Verificar se o usuário possui pendências de devolução.
* **Regras Relacionadas:** RN02 (Bloqueio de Usuários Inadimplentes).
* **Origem:** VD F2.1.

### RF05 - Confirmar Retirada de Ativo (Locação)

* **Descrição:** O sistema deve permitir que o **Atendente** confirme a entrega dos ativos ao professor mediante a conferência dos itens.
* **Ação Crítica:** Coletar o aceite digital do Termo de Responsabilidade.
* **Regras Relacionadas:** RN01 (Aceite de Termo de Responsabilidade).
* **Origem:** VD F2.2.

### RF06 - Transferir Ativo entre Professores

* **Descrição:** O sistema deve permitir que um **Professor (Cedente)** transfira a posse de um ativo diretamente para outro **Professor (Cessionário)** via aplicativo móvel.
* **Validação:** Exigir a leitura física da Tag NFC/QR Code pelo dispositivo do novo responsável.
* **Regras Relacionadas:** RN03 (Validação via Identificador Físico), RN04 (Notificação de Transferência).
* **Origem:** VD F2.3.

---

## 3. Devolução e Auditoria (Necessidade 3)

### RF07 - Registrar Devolução de Ativo

* **Descrição:** O sistema deve permitir que o **Atendente** registre a entrada de um ativo, encerrando o vínculo de responsabilidade do professor.
* **Ação Crítica:** Preencher o checklist de integridade física e avarias.
* **Regras Relacionadas:** RN05 (Checklist de Avarias), RN06 (Baixa Automática).
* **Origem:** VD F3.1.

### RF08 - Consultar Histórico de Movimentações

* **Descrição:** O sistema deve permitir que o **Administrador** visualize o rastro completo de um ativo: quem locou, quando transferiu e quem devolveu (com estado de conservação).
* **Origem:** VD F2.4, F3.2.

---

## 4. Notificações e Sistema (Necessidade 4)

### RF09 - Notificar Pendências e Atrasos

* **Descrição:** O sistema deve enviar alertas automáticos (Push/E-mail) para **Professores** com ativos atrasados e para a **Equipe de Atendimento** sobre o status do inventário.
* **Origem:** VD F4.1.

### RF10 - Sincronizar Movimentações Offline

* **Descrição:** O sistema deve permitir o registro de movimentações em modo offline e realizar o upload automático dos dados ao detectar conexão.
* **Consistência:** Validar conflitos de sincronização conforme prioridade de registro.
* **Origem:** Derivado do RNF04 e RNF05 para suporte à funcionalidade móvel.

---

## 5. Checklist de Validação (RF)

* [ ] Os requisitos funcionais estão alinhados com a Visão da Demanda.
* [ ] Cada RF possui uma descrição clara da ação e do ator.
* [ ] As regras de negócio (RN) foram referenciadas nos requisitos aplicáveis.
* [ ] Os requisitos são testáveis (ex: "O sistema deve permitir...").
* [ ] A numeração (RF01, RF02...) está sequencial e organizada por necessidade.
