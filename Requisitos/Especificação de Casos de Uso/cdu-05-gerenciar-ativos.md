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
