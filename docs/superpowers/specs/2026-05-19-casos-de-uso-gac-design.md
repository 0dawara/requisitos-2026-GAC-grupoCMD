# Especificação do Plano de Criação dos Casos de Uso (Projeto GAC)

## 1. Visão Geral
Este documento descreve o plano para a criação dos diagramas e da documentação detalhada dos Casos de Uso do projeto GAC, seguindo as diretrizes do projeto LAPIS. A abordagem escolhida foi a **Estrutura Granular**.

## 2. Estrutura de Arquivos Planejada

Os arquivos serão criados dentro do repositório `requisitos-2026-GAC-grupoCMD`.

### 2.1. Diagrama Visual (Mermaid)
Um único diagrama Mermaid que ilustra a relação entre os atores e os 6 casos de uso do sistema.
* **Caminho:** `Requisitos/Artefatos/Diagramas/cdu-gac-geral.mmd`

### 2.2. Especificações Textuais (Markdown)
Arquivos individuais baseados no template oficial do LAPIS (`template-cdu-caso-uso.md`).
* **Caminhos:**
  1. `Requisitos/Artefatos/CasosDeUso/cdu-01-solicitar-reserva.md` (Ator: Professor)
  2. `Requisitos/Artefatos/CasosDeUso/cdu-02-confirmar-locacao.md` (Ator: Atendente)
  3. `Requisitos/Artefatos/CasosDeUso/cdu-03-transferir-ativo.md` (Ator: Professor)
  4. `Requisitos/Artefatos/CasosDeUso/cdu-04-registrar-devolucao.md` (Ator: Atendente)
  5. `Requisitos/Artefatos/CasosDeUso/cdu-05-gerenciar-ativos.md` (Ator: Administrador)
  6. `Requisitos/Artefatos/CasosDeUso/cdu-06-auditar-movimentacoes.md` (Ator: Administrador)

## 3. Conteúdo Previsto por Caso de Uso

Cada arquivo `.md` seguirá a estrutura mínima:
1. **Nome do Caso de Uso:** (ex: CDU-01 - Solicitar Reserva)
2. **Objetivo:** Descrição clara da funcionalidade.
3. **Tipo:** Concreto.
4. **Atores:** Primário e Secundários (se houver).
5. **Precondições:** Estado inicial necessário.
6. **Fluxo Principal:** Passo a passo da interação (alternando entre ator e sistema).
7. **Fluxos Alternativos:** Variações comuns (ex: inativar ao invés de atualizar no CDU-05).
8. **Fluxos de Exceção:** Tratamento de erros (ex: ativo indisponível, usuário bloqueado).
9. **Pós-condições:** Estado final esperado.
10. **Requisitos Não Funcionais:** Referências ao RNF aplicável.

## 4. Próximos Passos
Após a aprovação deste documento, a implementação será iniciada através da criação simultânea ou sequencial destes 7 arquivos.
