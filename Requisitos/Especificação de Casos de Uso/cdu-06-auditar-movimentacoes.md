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
