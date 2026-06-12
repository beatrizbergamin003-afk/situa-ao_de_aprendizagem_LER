# 🚗 QuickParking – Sistema de Gestão de Estacionamento

## 👥 Integrantes

* Beatriz Neves Bergamin
* João Wictor

---

# 📖 1. Introdução

## 1.1 Objetivo

Este documento apresenta a **Especificação de Requisitos de Software (ERS)** do sistema **QuickParking**, desenvolvido para gerenciar o estacionamento de uma loja de conveniência localizada em um posto de combustível.

O sistema tem como objetivo controlar a entrada e saída de veículos, monitorar vagas disponíveis, calcular automaticamente valores de permanência, aplicar regras de negócio e gerar relatórios administrativos de faturamento.

---

## 1.2 Escopo

O QuickParking será responsável por:

* Controlar 20 vagas de estacionamento;
* Registrar veículos estacionados;
* Gerenciar entrada e saída de veículos;
* Calcular valores automaticamente;
* Controlar lotação;
* Aplicar multas por estacionamento irregular;
* Gerar relatórios financeiros;
* Fornecer acesso administrativo.

---

## 1.3 Definições

| Termo | Significado                             |
| ----- | --------------------------------------- |
| RF    | Requisito Funcional                     |
| RN    | Regra de Negócio                        |
| RNF   | Requisito Não Funcional                 |
| ERS   | Especificação de Requisitos de Software |
| CLI   | Interface por Linha de Comando          |

---

# 🖥️ 2. Visão Geral do Sistema

O QuickParking será um sistema desenvolvido em **Python** para auxiliar o controle operacional de um estacionamento de pequeno porte.

### Capacidade do Estacionamento

* 20 vagas no total;
* 15 vagas para carros, picapes e caminhões;
* 5 vagas exclusivas para motocicletas.

O sistema deverá controlar a ocupação das vagas em tempo real, garantindo que o limite máximo de capacidade não seja ultrapassado.

---

## 2.1 Usuários do Sistema

### Operador

Responsável por:

* Registrar entradas;
* Registrar saídas;
* Consultar vagas;
* Consultar veículos estacionados.

### Administrador

Responsável por:

* Consultar faturamento;
* Gerar relatórios;
* Visualizar movimentações;
* Gerenciar informações do sistema.

---

# 📋 3. Levantamento de Requisitos

## 3.1 Design Thinking

### Empatia

Durante o levantamento de requisitos, o cliente informou as seguintes necessidades:

* Controle de vagas ocupadas e livres;
* Registro da placa dos veículos;
* Controle de horário de entrada e saída;
* Cobrança automática;
* Controle de caminhões grandes;
* Relatórios financeiros;
* Aplicação de penalidades.

---

### Brainstorming

Funcionalidades levantadas:

* Cadastro de veículos;
* Controle de lotação;
* Controle de vagas;
* Relatório diário;
* Painel administrativo;
* Sistema de multas;
* Consulta de veículos estacionados;
* Controle de horários.

---

### Definição do Problema

O estacionamento não possui um sistema automatizado para controlar a movimentação dos veículos, resultando em dificuldades no gerenciamento das vagas e no cálculo das cobranças.

---

## 3.2 Briefing do Projeto

### Nome

**QuickParking**

### Cliente

Loja de Conveniência de Posto de Combustível

### Problema

Necessidade de controlar vagas, registrar veículos e calcular cobranças automaticamente.

### Solução

Desenvolvimento de um sistema em Python capaz de gerenciar todo o fluxo do estacionamento.

---

# 👤 4. Histórias de Usuário

### US01

Como operador, eu quero registrar a entrada dos veículos para controlar a ocupação das vagas.

### US02

Como operador, eu quero registrar a saída dos veículos para calcular automaticamente o valor devido.

### US03

Como cliente, eu quero ter gratuidade de até 15 minutos para realizar paradas rápidas.

### US04

Como administrador, eu quero visualizar o faturamento diário para acompanhar os resultados financeiros.

### US05

Como operador, eu quero visualizar vagas disponíveis para organizar melhor o estacionamento.

### US06

Como administrador, eu quero bloquear veículos acima de 12 metros para respeitar os limites físicos das vagas.

### US07

Como operador, eu quero identificar veículos estacionados irregularmente para aplicar penalidades.

---

# ⚙️ 5. Requisitos Funcionais

## RF01 – Registrar Entrada

O sistema deverá registrar:

* Placa;
* Tipo do veículo;
* Comprimento;
* Data e hora de entrada.

---

## RF02 – Questionário do Veículo

O sistema deverá solicitar:

* Moto;
* Carro;
* Picape;
* Caminhão.

Caso seja caminhão, deverá ser informado o comprimento.

---

## RF03 – Validar Comprimento

O sistema deverá impedir a entrada de veículos com comprimento superior a 12 metros.

---

## RF04 – Controle de Vagas

O sistema deverá controlar:

* 15 vagas para carros, picapes e caminhões;
* 5 vagas para motocicletas.

---

## RF05 – Sinalização de Vagas

O sistema deverá exibir:

* Vagas ocupadas;
* Vagas disponíveis;
* Veículos estacionados.

---

## RF06 – Controle de Lotação

O sistema deverá impedir novas entradas quando todas as 20 vagas estiverem ocupadas.

---

## RF07 – Registro de Saída

O sistema deverá registrar a saída do veículo e calcular o tempo de permanência.

---

## RF08 – Cálculo Automático

O sistema deverá calcular automaticamente o valor da permanência.

---

## RF09 – Horário de Funcionamento

O sistema deverá permitir entradas apenas entre:

* 05:00
* 22:00

---

## RF10 – Aplicação de Multas

O sistema deverá registrar multas para veículos estacionados em locais não permitidos.

---

## RF11 – Relatório Diário

O sistema deverá gerar relatórios contendo:

* Total de veículos;
* Quantidade de motos;
* Quantidade de carros;
* Quantidade de caminhões;
* Total arrecadado;
* Quantidade de multas.

---

# 📌 6. Regras de Negócio

| Código | Regra                                                                        |
| ------ | ---------------------------------------------------------------------------- |
| RN01   | Veículos com permanência de até 15 minutos não pagarão estacionamento.       |
| RN02   | A primeira hora terá custo de R$ 10,00.                                      |
| RN03   | Cada hora adicional terá custo de R$ 5,00.                                   |
| RN04   | A capacidade máxima do estacionamento é de 20 vagas.                         |
| RN05   | Motocicletas deverão ocupar exclusivamente as vagas destinadas a motos.      |
| RN06   | Veículos acima de 12 metros não poderão entrar.                              |
| RN07   | Todas as vagas possuem largura padrão de 2 metros.                           |
| RN08   | O estacionamento funcionará apenas das 05:00 às 22:00.                       |
| RN09   | Veículos estacionados em áreas proibidas estarão sujeitos à multa adicional. |

---

# 🔒 7. Requisitos Não Funcionais

## RNF01 – Desempenho

O sistema deverá responder às operações em até 2 segundos.

### RNF02 – Segurança

O acesso administrativo deverá exigir autenticação por usuário e senha.

### RNF03 – Usabilidade

O sistema deverá possuir interface simples e intuitiva.

### RNF04 – Confiabilidade

Os dados cadastrados deverão permanecer armazenados sem perda de informações.

### RNF05 – Manutenibilidade

O código deverá ser organizado utilizando:

* Funções;
* Listas;
* Dicionários;
* Tratamento de exceções.

---

# 🎨 8. Prototipação do Sistema

## Ferramenta Utilizada

**Figma**

### Objetivo

Representar visualmente o funcionamento do sistema antes da implementação.

### Telas Desenvolvidas

#### Tela de Entrada

Cadastro da placa, tipo e comprimento do veículo.

#### Tela de Validação

Bloqueio de veículos acima de 12 metros.

#### Tela de Registro

Associação do veículo a uma vaga.

#### Tela de Saída

Localização do veículo e cálculo da permanência.

#### Tela de Pagamento

Exibição do valor total e confirmação da cobrança.

#### Tela de Login

Acesso administrativo.

#### Tela Administrativa

Visualização de faturamento e movimentações.

---

## Fluxo do Sistema

```text
Cadastro do veículo
        ↓
Validação do comprimento
        ↓
Registro da entrada
        ↓
Ocupação da vaga
        ↓
Registro da saída
        ↓
Cálculo automático
        ↓
Pagamento
        ↓
Liberação da vaga
        ↓
Atualização do faturamento
```

---

## Figura 1 – Protótipo do Sistema

<img width="1380" height="550" alt="Captura de tela 2026-06-12 134649" src="https://github.com/user-attachments/assets/69bf08f1-6ca9-477b-9d6d-71975c8e7a88" />


---

# 🚀 9. Planejamento Ágil

## Kanban

### Backlog

* Levantamento de requisitos;
* Briefing;
* User Stories;
* Protótipo;
* Desenvolvimento;
* Testes;
* Documentação.

### To Do

* Desenvolvimento do relatório financeiro.

### Doing

* Implementação das funcionalidades.

### Done

* Requisitos;
* Protótipo;
* Planejamento.

---

## Scrum

### Sprint 1 (2 horas)

* Levantamento de requisitos;
* Design Thinking;
* Briefing;
* User Stories;
* Protótipo.

### Sprint Review

Validação dos requisitos com o professor.

### Sprint 2 (2 horas)

* Desenvolvimento;
* Testes;
* Correções;
* Documentação.

---

# ✅ 10. Critérios de Aceitação

O sistema será considerado aprovado quando:

* Controlar corretamente as 20 vagas;
* Diferenciar vagas de motos e veículos maiores;
* Impedir entrada após lotação máxima;
* Impedir entrada de veículos acima de 12 metros;
* Aplicar corretamente a gratuidade de 15 minutos;
* Calcular corretamente os valores cobrados;
* Registrar placas e horários;
* Exibir vagas ocupadas e disponíveis;
* Gerar relatório diário de faturamento;
* Aplicar multas por estacionamento irregular;
* Bloquear entradas fora do horário de funcionamento.

---

# 🏁 11. Considerações Finais

O sistema **QuickParking** foi projetado para atender às necessidades de gerenciamento de um estacionamento de loja de conveniência, proporcionando maior controle operacional, organização das vagas e precisão na cobrança dos clientes.


