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
