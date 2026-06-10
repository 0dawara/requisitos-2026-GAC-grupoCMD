# 🏢 PITCH: Sistema de Gestão de Ativos do CCT (GAC)

**Desenvolvido por:** Thiago Leal Menezes e Victor Carvalho Crispim de Souza (Grupo CMD).  
**Apresentado para:** Universidade de Fortaleza (UNIFOR) - Centro de Ciências Tecnológicas (CCT).

---

## 1️⃣ O Problema

O controle de ativos (projetores, cabos e chaves) no CCT baseia-se atualmente em formulários de papel (Termos de Saída e Entrada), gerando sérios problemas operacionais:

- 📋 **Controle Manual e Propenso a Erros:** Formulários de papel com preenchimento apressado, caligrafias ilegíveis e dados desatualizados criam "pontos cegos" na rastreabilidade do inventário.
- 🔄 **Transferências sem Rastreabilidade:** Movimentações de equipamentos entre professores e salas ocorrem sem registro formal, sem responsabilização definida.
- 🔍 **Localização e Responsabilidade Desconhecidas:** Extrema dificuldade em identificar onde está cada equipamento, quem é o responsável atual e qual o seu estado de conservação.
- ⚠️ **Ausência de Notificações e Alertas:** Não há lembretes automáticos para atrasos de devolução ou inconsistências operacionais no inventário.
- 🔒 **Fragilidade Jurídica:** A ausência de Termo de Responsabilidade Eletrônico dificulta a responsabilização formal em casos de danos ou perdas de patrimônio institucional.

---

## 2️⃣ Público-Alvo

- 👨‍🏫 **Professor (Prioridade Alta):** Docente do CCT que precisa locar e devolver ativos com agilidade entre turnos, sem burocracias demoradas, podendo transferir responsabilidade diretamente para outro professor via NFC ou QR Code.
- 🖥️ **Atendente (Prioridade Alta):** Funcionário administrativo responsável por validar movimentações no balcão, conferindo o kit de itens na entrega e preenchendo o checklist de avarias na devolução.
- 🏢 **Administrador / Coordenação (Prioridade Alta):** Responsável por manter a base de dados confiável, monitorar o ciclo de vida dos ativos e realizar auditorias através do histórico completo de movimentações.
- 🏛️ **Diretoria do CCT (Patrocinador):** Busca segurança patrimonial, responsabilização institucional e redução de perdas financeiras com a adoção de um processo digital e rastreável.

---

## 3️⃣ A Solução Proposta

Uma **plataforma digital integrada a identificadores físicos (NFC e QR Code)** que substitui os formulários de papel por um processo 100% digital, fundamentada na **Tríade da Rastreabilidade**:

- 📱 **Usabilidade:** App mobile com leitura de NFC/QR Code para agilizar a retirada e devolução de ativos sem interromper a rotina de aulas dos professores.
- ⚙️ **Operação:** Checklist digital obrigatório na devolução garante a conferência exata do estado físico dos equipamentos em cada movimentação.
- 🔒 **Auditoria:** Login institucional vinculado a um Termo de Responsabilidade Eletrônico e histórico imutável de movimentações garantem responsabilização e rastreabilidade totais.

**Stack tecnológico proposto:** Google Stitch (prototipação), Flutter (Mobile Android/iOS e Web) e Firebase (BaaS — autenticação, banco de dados em tempo real e notificações push).

---

## 4️⃣ Funcionalidades Principais

- 📦 **Gestão de Inventário (RF01–RF03):** CRUD completo de Projetores, Cabos e Chaves com número de patrimônio, Tag NFC/QR Code, inativação justificada e histórico de cadastro para auditoria.
- 📝 **Solicitação de Reserva (RF04):** O Professor solicita ativos disponíveis para um horário e sala específicos diretamente pelo app mobile.
- ✅ **Confirmação de Locação (RF05):** O Atendente valida pendências do professor e coleta o aceite digital do Termo de Responsabilidade antes de liberar os equipamentos.
- 🔄 **Transferência entre Professores (RF06):** Repasse de posse via leitura de NFC/QR Code pelo dispositivo do novo responsável, com registro de rastreabilidade imediato.
- 📥 **Registro de Devolução (RF07):** O Atendente registra a entrada e preenche o checklist de integridade física e avarias, encerrando formalmente o vínculo de responsabilidade.
- 🔍 **Auditoria de Movimentações (RF08):** O Administrador visualiza o rastro completo de cada ativo: quem locou, quando transferiu e em que estado foi devolvido.
- 🔔 **Alertas e Notificações (RF09):** Lembretes automáticos (Push/E-mail) para professores com ativos em atraso e alertas para a equipe de atendimento sobre o status do inventário.
- 📴 **Modo Offline (RF10):** Registro de movimentações sem conexão com sincronização automática ao detectar rede, garantindo operação contínua.

---

## 5️⃣ Benefícios e Impacto

**Para a Instituição (Diretoria e Setor de Patrimônio):**
- ✅ Responsabilização formal garantida pelo Termo de Responsabilidade Eletrônico juridicamente válido.
- ✅ Drástica redução de perdas, extravios e custos com reposição de equipamentos não identificados.

**Para a Gestão (Administrador / Coordenação):**
- ✅ Inventário sempre atualizado com rastreabilidade em tempo real de todos os ativos.
- ✅ Auditoria simplificada: histórico completo de locações, transferências e devoluções em um só lugar.

**Para a Operação (Professores e Atendentes):**
- ✅ Processo ágil e sem papel — retirada e devolução em segundos com NFC ou QR Code.
- ✅ Transferências entre professores 100% digitais, sem necessidade de retornar à secretaria.

**Impacto Geral:**
- 🌱 **Paperless:** Eliminação total dos formulários de papel e dos "pontos cegos" de rastreabilidade.
- 🏫 **Qualidade de Ensino:** Equipamentos organizados e disponíveis, reduzindo atrasos e indisponibilidade nas aulas.
- ⚖️ **Segurança Jurídica:** Conformidade com as exigências institucionais sobre responsabilidade patrimonial.

---

## 6️⃣ Proposta de Valor

> *"Substituir o controle manual e fragmentado de ativos do CCT por uma plataforma digital integrada a NFC e QR Code, garantindo rastreabilidade em tempo real, responsabilização formal e agilidade operacional para professores, atendentes e gestores."*

---

## 7️⃣ Próximos Passos (Roadmap)

1. 🤝 **Validação com Stakeholders** — Apresentação e refinamento dos protótipos com Professores, Atendentes e Diretoria do CCT
2. ⚙️ **Desenvolvimento do MVP** — Implementação do fluxo principal (reserva, confirmação, transferência e devolução) com Flutter e Firebase
3. 🎓 **Treinamento** — Capacitação de professores e atendentes antes do lançamento
4. 🚀 **Lançamento Gradual** — Implantação piloto no CCT com suporte completo
5. 📈 **Monitoramento e Melhorias** — Ajustes contínuos conforme feedback dos usuários
