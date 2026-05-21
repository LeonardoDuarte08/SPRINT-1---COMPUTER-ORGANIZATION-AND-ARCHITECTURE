# SPRINT-1---COMPUTER-ORGANIZATION-AND-ARCHITECTURE

## Integrantes

- Leonardo Gabriel Sá Duarte — RM 569029
- Timoteo de Andrade Romano — RM 569711
- Bruno Albuquerque Aguiar — RM 569035
- João Pedro Conturbia — RM 569788
- Eduardo Oliveira  — RM 570374
- Enzo De Nadai - RM 569985

---

# Objetivo do Projeto

O projeto tem como objetivo propor uma solução computacional eficiente para eletropostos de veículos elétricos, utilizando conceitos de arquitetura de computadores, sistemas embarcados e programação em Assembly.

A proposta busca melhorar a eficiência energética e reduzir desperdícios computacionais através de um sistema inteligente de distribuição de carga baseado em arquitetura RISC-V.

---

# Problema Identificado

Muitos eletropostos utilizam softwares de alto nível e hardware genérico para controlar carregadores e processar dados.

Isso gera:

- Maior consumo computacional
- Overhead de software
- Desperdício de energia
- Baixa eficiência no processamento
- Sobrecarga da infraestrutura elétrica

Além disso, quando vários veículos carregam simultaneamente, a distribuição de potência pode ocorrer de forma ineficiente. Podendo até mesmo sobrecarregar o sistema, utilizando até mais energia do que é necessário.

---

# Proposta de Solução

Desenvolvemos uma proposta de sistema embarcado utilizando:

- Microcontrolador RISC-V
- Código otimizado em Assembly
- Leitura inteligente de sensores
- Controle dinâmico de distribuição de carga

O sistema monitora:
- carregadores ativos;
- corrente elétrica;
- tensão da rede;
- energia disponível.

Com base nessas informações, o sistema redistribui automaticamente a potência disponível entre os carregadores ativos.

### Funcionamento

- Poucos carregadores ativos → maior potência individual
- Muitos carregadores ativos → potência dividida proporcionalmente

O objetivo é evitar desperdícios, reduzir sobrecarga e melhorar a eficiência energética do eletroposto.

---

# Arquitetura Utilizada

## Arquitetura RISC-V

Escolhemos a arquitetura RISC-V por conta de:

- baixo consumo energético;
- conjunto reduzido de instruções;
- eficiência para sistemas embarcados;
- execução mais simples e previsível;
- arquitetura open source.

---

# Conceitos Aplicados

O projeto utiliza conceitos de:

- Arquitetura RISC
- Pipeline de instruções
- Eficiência computacional
- Sistemas embarcados
- Programação em Assembly
- Controle em tempo real
- Sustentabilidade computacional

---

# Pipeline de Processamento

O pipeline organiza a execução das instruções em etapas:

1. Fetch
O processador busca a próxima instrução na memória.

2. Decode
A instrução é interpretada para identificar qual operação deve ser executada.

3. Execute
A operação lógica ou aritmética é realizada pelo processador.

4. Memory Access
O sistema acessa dados necessários na memória, caso necessário.

5. Write Back
O resultado da operação é armazenado nos registradores.

Esse modelo melhora:
- eficiência do processador;
- velocidade de resposta;
- aproveitamento de energia.

---

# Código Assembly (Exemplo bem simples que fizemos)

lw t0, 0x00(a0)      ; leitura do sensor
add s0, s0, t0       ; soma demanda
addi s1, s1, 1       ; conta carregadores
div a2, s2, s1       ; calcula carga por carregador
sw a2, PWM_CTRL(a0)  ; aplica potência
