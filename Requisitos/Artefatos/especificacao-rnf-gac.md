# Especificação de Requisitos Não Funcionais - Projeto GAC

> **Sistema de Gestão de Ativos do CCT (GAC)**
>
> Este documento define os requisitos não funcionais para a plataforma GAC, focando em garantir agilidade, confiabilidade e segurança no controle de ativos da Unifor.

## Histórico de Versões

| Data       | Versão | Descrição                                                      | Autor     |
| ---------- | ------ | -------------------------------------------------------------- | --------- |
| 19/05/2026 | 1.0    | Criação inicial baseada nos templates LAPIS e demandas do CCT. | Grupo CMD |

## 1. Requisitos de Produto

### 1.1. Eficiência de Desempenho

#### 1.1.1. Comportamento temporal

* **RNF01 - Sincronização em Segundo Plano:** O sistema deve detectar o restabelecimento da conexão e iniciar a sincronização dos dados pendentes automaticamente em até **30 segundos**.

#### 1.1.2. Capacidade

* **RNF02 - Usuários Simultâneos:** O sistema deve suportar até **200 usuários simultâneos** no ambiente web sem degradação perceptível de performance.
* **RNF03 - Taxa de Transações Mobile:** O sistema deve processar até **50 operações de locação/minuto** via interface mobile durante horários de pico.

### 1.2. Confiabilidade

#### 1.2.1. Resiliência Offline

* **RNF04 - Integridade na Sincronização:** Em caso de conflito de dados (ex: transferência offline vs. devolução online), o sistema deve priorizar o registro realizado pelo **Atendente** e gerar um alerta para o Administrador.

#### 1.2.2. Recuperabilidade

* **RNF05 - Backup Incrementais:** O sistema deve realizar cópias de segurança (backups) incrementais do banco de dados a cada **4 horas**.

### 1.3. Segurança

#### 1.3.1. Autenticação

* **RNF06 - Autenticação Persistente:** O aplicativo deve permitir que o Professor permaneça autenticado para facilitar o uso durante múltiplos turnos, garantindo acesso às funcionalidades críticas mesmo em modo offline.

#### 1.3.2. Termo Eletrônico

* **RNF07 - Aceite de Termos:** O usuário deve aceitar obrigatoriamente o Termo de Responsabilidade antes de realizar sua primeira operação na plataforma.

#### 1.3.3. Confidencialidade

* **RNF08 - Criptografia de Dados Locais:** Dados sensíveis armazenados localmente nos dispositivos móveis devem ser protegidos por criptografia de padrão industrial.

### 1.4. Compatibilidade

#### 1.4.1. Adaptabilidade

* **RNF09 - Versões de SO:** O aplicativo mobile deve ser compatível com **Android 9.0+** e **iOS 13+**.
* **RNF10 - Suporte NFC:** O sistema deve garantir compatibilidade com as APIs de NFC modernas para leitura de etiquetas de ativos.

---

## 4. Checklist de Validação (RNF)

* [x] O documento possui histórico de versões preenchido.
* [x] Requisitos de operação offline e sincronização estão detalhados.
* [x] As métricas de desempenho (RNF01, RNF02, RNF03) são verificáveis.
* [x] A segurança da assinatura eletrônica foi definida adequadamente.
* [x] O artefato segue o padrão visual e de estrutura do projeto.
