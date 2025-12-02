# Otimização da Tarifa de Pico no Consumo de Energia Elétrica  
**com validação por dados reais do ONS**

Projeto acadêmico desenvolvido por **Igor Cecim** e **Eduardo Rodrigues** no 2º bimestre, com foco em modelagem matemática e implementação de um sistema full stack para otimização tarifária em horário de pico. :contentReference[oaicite:0]{index=0}

---

## Sumário
- [Visão Geral](#visão-geral)
- [Objetivos](#objetivos)
- [Prospecção do Problema (PBL)](#prospecção-do-problema-pbl)
- [Persona e Contexto](#persona-e-contexto)
- [Modelagem Matemática](#modelagem-matemática)
- [Validação com Dados Reais (ONS – 2024)](#validação-com-dados-reais-ons--2024)
- [Sistema Desenvolvido (Full Stack)](#sistema-desenvolvido-full-stack)
- [Resultados](#resultados)
- [Limitações](#limitações)
- [Trabalhos Futuros](#trabalhos-futuros)
- [Conclusão](#conclusão)
- [Referências](#referências)

---

## Visão Geral

A tarifa de pico (Time of Use – TOU) é um instrumento de controle de demanda no setor elétrico, criado para **desestimular o consumo elevado em horários críticos**. Essa estratégia reduz sobrecarga na rede e custos operacionais, ao incentivar o deslocamento do consumo para horários fora do pico.

Neste projeto, foi construída uma modelagem matemática para **otimizar o preço da tarifa de pico**, maximizando o lucro da concessionária, e validando a coerência do modelo com dados reais do **Operador Nacional do Sistema Elétrico (ONS)**. :contentReference[oaicite:1]{index=1}

---

## Objetivos

- Modelar matematicamente a relação entre **preço da tarifa de pico** e **consumo de energia**.
- Determinar o **preço ótimo** que maximiza o lucro.
- Comparar diferentes modelos de demanda.
- Validar a solução com dados reais do ONS (Curva de Carga Horária 2024).
- Implementar um sistema web full stack para automatizar o cálculo do preço ótimo. :contentReference[oaicite:2]{index=2}

---

## Prospecção do Problema (PBL)

O aumento do consumo nos horários de pico exige mecanismos de gestão eficientes. Estudos sobre **elasticidade da demanda** e **tarifação dinâmica** mostram que a demanda é influenciada diretamente pelo preço.

Dessa forma, foi escolhido o problema de otimização da tarifa de pico usando ferramentas de cálculo (funções, derivadas e maximização de lucro), respeitando a operação do sistema elétrico. :contentReference[oaicite:3]{index=3}

---

## Persona e Contexto

A persona definida foi:

**Maria Silva** — Diretora de planejamento da concessionária fictícia *Amazônia Luz Distribuidora*.

- **Dor principal:** sobrecarga do sistema às **19h**, horário real de pico no Brasil.
- **Objetivo:** definir uma tarifa que reduza a demanda no pico sem prejudicar o lucro da empresa. :contentReference[oaicite:4]{index=4}

---

## Modelagem Matemática

### Variável de decisão
- **p** = preço da tarifa de pico *(R$/MWh)*

### Demanda no pico
A demanda depende do preço:
- **q(p)**

### Modelos de demanda considerados
- **Linear**
- **Exponencial**
- **Potência**
- **Logarítmico** :contentReference[oaicite:5]{index=5}

### Função lucro
Com:
- **Cf** = custo fixo  
- **c** = custo marginal constante  

Lucro:
\[
L(p) = p\cdot q(p) - (Cf + c\cdot q(p))
\]

### Condição de ótimo
O preço ótimo é obtido por:
\[
\frac{dL}{dp} = 0
\]

A partir dessa condição, o sistema calcula automaticamente o **preço ótimo** para cada modelo de demanda. :contentReference[oaicite:6]{index=6}

---

## Validação com Dados Reais (ONS – 2024)

Os dados foram coletados da base:

- **Curva de Carga Horária – 2024 (ONS)**
- Variável usada: **val_cargaenergiahomwmed** *(MW)*

### Distribuição observada
- **Demanda mínima:** 67.668,53 MW às **04h**
- **Demanda máxima:** 87.569,90 MW às **19h**
- **Período de pico identificado:** **18h–21h**

Esses dados calibraram a função demanda e garantiram validação empírica do modelo. :contentReference[oaicite:7]{index=7}

---

## Sistema Desenvolvido (Full Stack)

### Tecnologias

**Frontend**
- HTML
- CSS
- JavaScript

**Backend**
- FastAPI (Python)

**Otimização simbólica**
- SymPy :contentReference[oaicite:8]{index=8}

### Fluxo do sistema
1. O usuário insere parâmetros de demanda e custos no frontend.  
2. O backend processa a função e aplica a condição de ótimo.  
3. O sistema retorna o **preço ótimo p\*** e a justificativa matemática no frontend.

---

## Resultados

A solução determinou uma tarifa de pico ótima que:

- **maximiza o lucro da concessionária**,  
- **não agrava a sobrecarga da rede**,  
- e apresenta coerência com a curva real de consumo validada pelo ONS. :contentReference[oaicite:9]{index=9}

---

## Limitações

- Considera comportamento linear/simplificado de demanda.  
- Assume custo marginal constante.  
- Não inclui fatores externos (clima, economia, comportamento social), que podem alterar a demanda real. :contentReference[oaicite:10]{index=10}

---

## Trabalhos Futuros

Sugestões de evolução do projeto:

- Aplicação de modelos exponenciais mais robustos.  
- Inclusão explícita de **elasticidade-preço**.  
- Persistência em banco de dados.  
- Dashboards gráficos para visualização de lucro e demanda. :contentReference[oaicite:11]{index=11}

---

## Conclusão

O projeto alcançou os objetivos propostos ao integrar:

**modelagem matemática + validação real com dados do ONS + implementação full stack**, oferecendo uma ferramenta prática para apoiar decisões tarifárias em horários de pico. :contentReference[oaicite:12]{index=12}

---

## Referências

- ONS – Operador Nacional do Sistema Elétrico.  
  **Curva de Carga Horária – 2024.**  
  https://dados.ons.org.br/dataset/curva-carga

