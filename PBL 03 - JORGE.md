
## Tema

Grau de Liberdade e Estratégias de Resolução de Problemas

---

# Contexto

Neste problema temos uma unidade de processo que recebe uma corrente de alimentação formada por água, etanol e metanol.
Essa corrente passa por uma unidade de processo e depois é dividida em duas correntes de saída.
Antes de começar os cálculos, precisamos verificar se as informações fornecidas são suficientes para determinar todas as variáveis do processo.
Por isso, a primeira etapa é identificar as informações conhecidas, as incógnitas e as relações que podem ser utilizadas.
A ideia principal é verificar o **grau de liberdade do sistema**, ou seja, descobrir se temos equações suficientes para determinar todas as incógnitas.

---

#  Etapa 1 — Representação do Processo

Podemos representar o processo de forma simplificada da seguinte maneira:

```text
                  Corrente de alimentação
                  F = ? kg/h
                  H₂O = 60%
                  Etanol = 25%
                  Metanol = 15%
                         │
                         ▼
                ┌─────────────────┐
                │ Unidade de      │
                │ processo        │
                └─────────────────┘
                    │         │
                    ▼         ▼
              Corrente 1   Corrente 2
              F₁ = 500 kg/h F₂ = ? kg/h
              composição ?  H₂O = 30%
                            Etanol = 40%
                            Metanol = 30%
```
A Corrente 1 possui vazão conhecida de **500 kg/h**, porém sua composição é desconhecida.

A Corrente 2 possui composição conhecida, mas sua vazão é desconhecida.

---

# Etapa 2 — Identificação das Variáveis

Primeiro vamos separar aquilo que já conhecemos das informações que ainda precisam ser determinadas.

## Variáveis conhecidas

### Corrente de alimentação

* Fração mássica de água = **0,60**
* Fração mássica de etanol = **0,25**
* Fração mássica de metanol = **0,15**
* Vazão total = **desconhecida**

### Corrente 1

* Vazão = **500 kg/h**
* Composição = **desconhecida**

### Corrente 2

* Fração mássica de água = **0,30**
* Fração mássica de etanol = **0,40**
* Fração mássica de metanol = **0,30**
* Vazão = **desconhecida**

---

## Variáveis desconhecidas

Podemos representar a vazão da alimentação por:

**F = vazão da alimentação**

A vazão da Corrente 2 será:

**F₂ = vazão da Corrente 2**

Na Corrente 1, podemos representar as frações mássicas por:

* **x₁,H₂O** = fração mássica de água;
* **x₁,EtOH** = fração mássica de etanol;
* **x₁,MeOH** = fração mássica de metanol.

Como a soma das frações mássicas precisa ser igual a 1:

**x₁,H₂O + x₁,EtOH + x₁,MeOH = 1**

Portanto, somente duas das três composições da Corrente 1 são independentes.

Assim, podemos considerar inicialmente as quatro incógnitas:

* **F**
* **F₂**
* **x₁,H₂O**
* **x₁,EtOH**

A fração de metanol pode ser encontrada pela relação de composição.

---

# Etapa 3 — Relações Físicas

Para analisar o processo podemos utilizar os balanços de massa.

Como não existe nenhuma informação sobre reação química ou geração de massa, podemos considerar que a massa que entra no sistema deve ser igual à massa que sai.

## Balanço global de massa

A relação geral será:

**F = F₁ + F₂**

Como a Corrente 1 possui vazão de 500 kg/h:

**F = 500 + F₂**

---

## Balanço de água

A alimentação possui 60% de água.

Portanto:

**0,60F = 500x₁,H₂O + 0,30F₂**

---

## Balanço de etanol

A alimentação possui 25% de etanol:

**0,25F = 500x₁,EtOH + 0,40F₂**

---

## Balanço de metanol

A alimentação possui 15% de metanol:

**0,15F = 500x₁,MeOH + 0,30F₂**

Além disso:

**x₁,H₂O + x₁,EtOH + x₁,MeOH = 1**

Essas são as principais relações que podem ser utilizadas para representar o processo.

---

# Etapa 4 — Grau de Liberdade

Agora podemos verificar se temos informações suficientes para resolver o problema.

Considerando como incógnitas independentes:

* **F**
* **F₂**
* **x₁,H₂O**
* **x₁,EtOH**

Temos:

**Número de incógnitas = 4**

Para essas quatro incógnitas, podemos utilizar três balanços de componentes:

1. balanço de água;
2. balanço de etanol;
3. balanço de metanol.

Portanto:

**Número de equações independentes = 3**

Utilizando:

**GL = Número de incógnitas − Número de equações independentes**

Temos:

**GL = 4 − 3**

**GL = 1**

---

# 📋 Etapa 5 — Diagnóstico

Como o grau de liberdade encontrado foi:

**GL = 1**

o sistema possui uma variável independente que ainda não pode ser determinada.

Portanto, o problema inicialmente é **subdeterminado**.

Isso significa que as informações fornecidas não são suficientes para determinar completamente todas as vazões e composições do processo.

Precisamos de pelo menos **uma informação independente adicional** para que o sistema possa ser determinado.

---

# Etapa 6 — Proposta da Equipe

A menor quantidade de informação adicional necessária é **uma informação independente**.

Uma possibilidade seria informar a vazão total da alimentação.

Com essa informação, a vazão da alimentação deixa de ser uma incógnita.

Assim, o sistema passa a possuir três incógnitas independentes:

* **F₂**
* **x₁,H₂O**
* **x₁,EtOH**

E três equações independentes.

Dessa forma, o grau de liberdade passa a ser zero.

Porém, ainda será necessário verificar se os resultados encontrados são fisicamente possíveis.

---

# Etapa 7 — Nova Informação

Agora recebemos a informação:

> **A vazão total da alimentação é 2000 kg/h.**

Então:

**F = 2000 kg/h**

A alimentação deixa de ser uma incógnita.

## Novas incógnitas

Continuamos com:

* **F₂**
* **x₁,H₂O**
* **x₁,EtOH**

A fração de metanol da Corrente 1 continua podendo ser encontrada pela relação:

**x₁,MeOH = 1 − x₁,H₂O − x₁,EtOH**

Portanto:

**Número de incógnitas = 3**

Temos três balanços de componentes independentes:

* água;
* etanol;
* metanol.

Logo:

**Número de equações independentes = 3**

Calculando o grau de liberdade:

**GL = 3 − 3**

**GL = 0**

Pelo grau de liberdade, o sistema agora é **determinado** do ponto de vista matemático.

Entretanto, ainda precisamos verificar se a solução obtida possui significado físico.

---

# Etapa 8 — Nova Informação

Agora recebemos mais uma informação:

> **A Corrente 1 possui 50% de água.**

Portanto:

**x₁,H₂O = 0,50**

Como a Corrente 1 possui três componentes, temos:

**x₁,H₂O + x₁,EtOH + x₁,MeOH = 1**

Substituindo:

**0,50 + x₁,EtOH + x₁,MeOH = 1**

Assim:

**x₁,EtOH + x₁,MeOH = 0,50**

## Novas incógnitas

Agora podemos considerar como incógnitas:

* **F₂**
* **x₁,EtOH**
* **x₁,MeOH**

Portanto:

**Número de incógnitas = 3**

Ainda podemos utilizar os três balanços de componentes.

Logo:

**Número de equações independentes = 3**

Então:

**GL = 3 − 3**

**GL = 0**

Novamente, temos um sistema determinado pelo grau de liberdade.

Porém, como a nova informação fixa a composição da Corrente 1, precisamos verificar se os dados são compatíveis entre si.

---

# Etapa 9 — Resolução

Agora temos todas as informações fornecidas até a Etapa 8:

### Alimentação

* Vazão = **2000 kg/h**
* Água = **60%**
* Etanol = **25%**
* Metanol = **15%**

### Corrente 1

* Vazão = **500 kg/h**
* Água = **50%**
* Etanol = **desconhecido**
* Metanol = **desconhecido**

### Corrente 2

* Água = **30%**
* Etanol = **40%**
* Metanol = **30%**
* Vazão = **desconhecida**

---

## 1. Balanço global

Primeiro podemos calcular a vazão da Corrente 2.

O balanço global é:

**F = F₁ + F₂**

Substituindo:

**2000 = 500 + F₂**

Então:

**F₂ = 2000 − 500**

**F₂ = 1500 kg/h**

Pelo balanço global, a Corrente 2 deveria possuir vazão de:

**F₂ = 1500 kg/h**

---

## 2. Balanço de água

A alimentação possui 60% de água.

Então a quantidade de água que entra é:

**mH₂O,entrada = 0,60 × 2000**

**mH₂O,entrada = 1200 kg/h**

Na Corrente 1, temos 50% de água:

**mH₂O,C1 = 0,50 × 500**

**mH₂O,C1 = 250 kg/h**

Na Corrente 2, considerando a vazão encontrada pelo balanço global:

**mH₂O,C2 = 0,30 × 1500**

**mH₂O,C2 = 450 kg/h**

Portanto, a quantidade de água que sairia do processo seria:

**250 + 450 = 700 kg/h**

Mas a alimentação possui:

**1200 kg/h de água**

Então:

**1200 ≠ 700**

Já encontramos uma inconsistência no balanço de água.

---

## 3. Balanço de etanol

A quantidade de etanol que entra é:

**mEtOH,entrada = 0,25 × 2000**

**mEtOH,entrada = 500 kg/h**

A quantidade de etanol que sairia pela Corrente 2 seria:

**mEtOH,C2 = 0,40 × 1500**

**mEtOH,C2 = 600 kg/h**

Para o balanço ser satisfeito:

**500 = mEtOH,C1 + 600**

Logo:

**mEtOH,C1 = 500 − 600**

**mEtOH,C1 = −100 kg/h**

Esse resultado não é fisicamente possível, pois uma vazão mássica não pode ser negativa.

Portanto, o balanço de etanol também mostra que os dados fornecidos são incompatíveis.

---

## 4. Balanço de metanol

A quantidade de metanol que entra é:

**mMeOH,entrada = 0,15 × 2000**

**mMeOH,entrada = 300 kg/h**

Na Corrente 2:

**mMeOH,C2 = 0,30 × 1500**

**mMeOH,C2 = 450 kg/h**

Assim:

**300 = mMeOH,C1 + 450**

Portanto:

**mMeOH,C1 = 300 − 450**

**mMeOH,C1 = −150 kg/h**

Novamente encontramos uma vazão negativa, o que não possui significado físico.

---

## 5. Verificação da composição da Corrente 1

Pela informação fornecida, a Corrente 1 possui 50% de água.

Como sua vazão é 500 kg/h:

**mH₂O,C1 = 0,50 × 500**

**mH₂O,C1 = 250 kg/h**

Como a quantidade total da Corrente 1 é 500 kg/h, restariam:

**500 − 250 = 250 kg/h**

para etanol e metanol.

Porém, os balanços dos componentes forneceram:

* Etanol = **−100 kg/h**
* Metanol = **−150 kg/h**

Somando:

**−100 + (−150) = −250 kg/h**

Esse resultado também não pode representar uma corrente física.

Portanto, os dados do problema não são fisicamente compatíveis entre si.

---

# 📊 Resultados encontrados

| Grandeza                                |     Resultado |
| --------------------------------------- | ------------: |
| Vazão da alimentação                    | **2000 kg/h** |
| Vazão da Corrente 1                     |  **500 kg/h** |
| Vazão da Corrente 2 pelo balanço global | **1500 kg/h** |
| Água na alimentação                     | **1200 kg/h** |
| Água na Corrente 1                      |  **250 kg/h** |
| Água na Corrente 2                      |  **450 kg/h** |
| Etanol na alimentação                   |  **500 kg/h** |
| Etanol na Corrente 2                    |  **600 kg/h** |
| Etanol calculado na Corrente 1          | **−100 kg/h** |
| Metanol na alimentação                  |  **300 kg/h** |
| Metanol na Corrente 2                   |  **450 kg/h** |
| Metanol calculado na Corrente 1         | **−150 kg/h** |

Os resultados negativos mostram que não existe uma solução fisicamente válida utilizando todas as informações fornecidas.

---

# Etapa 10 — Verificação

Agora precisamos verificar se a solução encontrada é fisicamente consistente.

## Balanço global

Temos:

**Entrada = 2000 kg/h**

E:

**Saída = 500 + 1500**

**Saída = 2000 kg/h**

Portanto, o **balanço global de massa esta ok!**.

---

## Balanço por componente

### Água

Entrada:

**1200 kg/h**

Saída:

**250 + 450 = 700 kg/h**

Logo:

**1200 ≠ 700**

O balanço de água não fecha.

---

### Etanol

Entrada:

**500 kg/h**

Na Corrente 2 já temos:

**600 kg/h**

Para fechar o balanço, seria necessário:

**500 − 600 = −100 kg/h**

Como não existe vazão mássica negativa em uma corrente comum, o resultado é fisicamente impossível.

---

### Metanol

Entrada:

**300 kg/h**

Na Corrente 2:

**450 kg/h**

Então seria necessário:

**300 − 450 = −150 kg/h**

Novamente encontramos um valor negativo, indicando inconsistência física.

---

## Composição

A composição da alimentação é:

* Água = **60%**
* Etanol = **25%**
* Metanol = **15%**

A composição da Corrente 2 é:

* Água = **30%**
* Etanol = **40%**
* Metanol = **30%**

Essas composições individualmente são válidas, pois todas as frações estão entre 0 e 1 e suas somas são iguais a 1.

Na Corrente 1, a informação de 50% de água também é possível isoladamente.

O problema acontece quando todas essas informações são consideradas simultaneamente nos balanços de massa.

---

## Consistência física

O principal problema aparece porque a Corrente 2, com vazão de 1500 kg/h, possui mais etanol e metanol do que existe disponível na alimentação.

Por exemplo, a alimentação possui somente:

**500 kg/h de etanol**

enquanto a Corrente 2 sozinha teria:

**600 kg/h de etanol**

Isso seria impossível sem que houvesse alguma fonte adicional de etanol no processo.

O mesmo acontece com o metanol:

**300 kg/h na alimentação**

contra:

**450 kg/h na Corrente 2**

Portanto, apesar de o grau de liberdade indicar um sistema determinado, os dados fornecidos não formam um processo fisicamente possível.

---

# Etapa 11 — Reflexão

## 1. Por que não é adequado começar os cálculos imediatamente?

Porque antes dos cálculos precisamos saber quais são as informações conhecidas e quais são as incógnitas.

Se começarmos diretamente pelas equações, podemos acabar utilizando informações de forma incorreta ou tentando resolver um sistema que não possui equações suficientes.

A análise inicial ajuda a entender a estrutura do problema antes de realizar os cálculos.

---

## 2. Qual foi a principal dificuldade encontrada na identificação das incógnitas?

A principal dificuldade foi perceber que as três composições da Corrente 1 não são totalmente independentes.

Como a soma das frações mássicas deve ser igual a 1, basta conhecer duas delas para determinar a terceira.

Por isso, precisamos tomar cuidado para não contar a mesma informação mais de uma vez.

---

## 3. Por que o grau de liberdade é importante para a resolução de um problema de engenharia?

O grau de liberdade mostra se temos informações suficientes para determinar as incógnitas.

Quando:

**GL > 0**

faltam informações.

Quando:

**GL = 0**

o sistema possui, em princípio, informações suficientes para determinar as incógnitas.

Quando:

**GL < 0**

há mais restrições do que incógnitas, sendo necessário verificar se as informações são compatíveis.

Por isso, o grau de liberdade é uma ferramenta importante para saber se vale a pena iniciar os cálculos ou se ainda precisamos de mais informações.

---

## 4. Qual informação foi necessária para tornar o problema determinado?

A primeira informação adicional necessária foi a **vazão total da alimentação**

Essa informação reduziu o número de incógnitas e fez o grau de liberdade passar de:

**GL = 1**

para:

**GL = 0**

Depois disso, a informação de que a Corrente 1 possui 50% de água permitiu uma nova análise da composição dessa corrente.

---

## 5. É possível obter uma resposta matemática e, ainda assim, ter um modelo fisicamente inconsistente?

Sim.

Esse foi justamente o caso encontrado neste problema.

O grau de liberdade chegou a zero, indicando que matematicamente existia um número suficiente de equações para determinar as incógnitas.

Porém, quando fizemos os balanços dos componentes, apareceram valores negativos para as vazões de etanol e metanol na Corrente 1.

Portanto, uma solução matemática não significa necessariamente que o resultado representa um processo físico possível.

É necessário sempre verificar os resultados.

---

## 6. Como a análise de grau de liberdade pode ajudar um engenheiro antes da execução de um projeto ou processo?

A análise de grau de liberdade permite verificar antecipadamente se as informações disponíveis são suficientes para realizar os cálculos.

Isso pode evitar perda de tempo com um problema que ainda possui informações faltantes.

Além disso, ela ajuda a identificar quais dados precisam ser obtidos antes de continuar a análise do processo.

No caso deste problema, foi possível perceber inicialmente que faltava uma informação para determinar completamente o sistema.

Também foi possível perceber depois que ter **GL = 0** não garante que os dados sejam fisicamente coerentes. Por isso, além do grau de liberdade, é necessário verificar os balanços e a consistência física dos resultados.

de, ele não representa um processo possível.
