# Sistema de Gestão de Ativos do CCT (GAC)

> Repositório do **Grupo CMD** (Thiago Leal Menezes e Victor Carvalho Crispim de Souza), dedicado à disciplina de **Requisitos e Modelagem de Sistemas**.

Este projeto tem como objetivo principal modelar e documentar detalhadamente os requisitos para um **Sistema de Gestão de Ativos (GAC)**. A plataforma visa facilitar, registrar e controlar o inventário, bem como o processo de empréstimo (locação) e devolução de equipamentos essenciais, tais como:

- 📽️ Projetores
- 🔌 Cabos de vídeo e energia (HDMI, VGA, etc.)
- 🖱️ Acessórios diversos (apontadores, adaptadores)
- 🔑 Chaves de laboratórios e salas

O sistema será utilizado para gerenciar os recursos físicos do **Centro de Ciências Tecnológicas (CCT)**, proporcionando mais controle, rastreabilidade e eficiência operacional.

---

## 🌐 Pitch Interativo

O pitch do projeto está disponível online via GitHub Pages:

> **[https://0dawara.github.io/requisitos-2026-GAC-grupoCMD/pitch.html](https://0dawara.github.io/requisitos-2026-GAC-grupoCMD/pitch.html)**

---

## 🛠️ Stack Tecnológica Proposta

| Camada | Tecnologia |
| :--- | :--- |
| Prototipação | Google Stitch |
| Mobile (Android/iOS) | Flutter |
| Web (Painel Administrativo) | Flutter Web |
| Backend / BaaS | Firebase (Auth, Firestore, Cloud Messaging) |
| Identificação Física | Tags NFC + QR Code |

---

## 📁 Estrutura do Repositório

A organização do repositório foi baseada em padrões de Liderança Ágil (modelo [LAPIS](https://github.com/ProfBezerra/LAPIS)).

- **[`pitch.html`](pitch.html)** / **[`pitch.md`](pitch.md)**  
  Apresentação interativa do projeto com protótipos embarcados.

- **[`assets/screens/`](assets/screens/)**  
  Protótipos de alta fidelidade gerados no Google Stitch (Dashboard, Scan NFC/QR, Termo de Responsabilidade, Checklist de Devolução).

- **[`Requisitos/`](Requisitos/)**  
  Toda a documentação de engenharia de requisitos do projeto.
  - [`SRS-IEEE-830.md`](Requisitos/SRS-IEEE-830.md) — Especificação completa no padrão IEEE 830.
  - `Elicitacao/` — Visão da Demanda, Glossário, Stakeholders e Roteiro de Entrevistas.
  - `Especificação de Casos de Uso/` — CDU-01 a CDU-06.
  - `Especificação de Regra de Negocio/` — RN01 a RN08.
  - `Requisitos Não Funcionais/` — RNF01 a RNF10.

---

## 🎯 Objetivo Acadêmico

Através da modelagem deste sistema, os integrantes do **Grupo CMD** aplicarão, na prática, técnicas de:

- Elicitação de Requisitos com Stakeholders.
- Documentação e Padronização de Artefatos.
- Modelagem de Sistemas utilizando UML.
- Definição de Regras de Negócio e Restrições Não Funcionais.

---

## ⚙️ Diretrizes de Contribuição

1. Todas as modificações documentais devem seguir os templates e padronizações estabelecidos.
2. Consulte o documento [`Requisitos/README.md`](Requisitos/README.md) para entender as boas práticas de versionamento dos artefatos.
