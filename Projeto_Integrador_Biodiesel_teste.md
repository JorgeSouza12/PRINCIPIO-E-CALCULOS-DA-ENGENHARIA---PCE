# Projeto Integrador — Produção de biodiesel por transesterificação

**Disciplina:** Princípios e Cálculos da Engenharia  
**Dupla 02:** Gustavo Souza e Jorge Souza

## 1. Fluxograma e fronteira do sistema

~~~mermaid
flowchart TB
    C1["Corrente 1 · Óleo vegetal (TG) · 800 kg/h · 25 °C"]
    C2["Corrente 2 · Metanol (CH₃OH) · 160 kg/h · 25 °C"]
    H["Calor fornecido · Q̇ (kJ/h)"]
    subgraph VC["Fronteira do volume de controle"]
        R["Reator de transesterificação · Base · 60 °C e conversão de TG de 75%"]
    end
    C3["Corrente 3 · TG + metanol + biodiesel + glicerol · Vazões em kg/h e kmol/h · 60 °C na base"]
    C1 --> R
    C2 --> R
    H -.-> R
    R --> C3
~~~

| Corrente | Sentido | Espécies | Vazão mássica (kg/h) | Vazão molar (kmol/h) |
|---|---|---|---:|---:|
| 1 | Entrada | TG | 800 | 0,904977 |
| 2 | Entrada | Metanol | 160 | 5,000000 |
| 3 | Saída | TG, metanol, biodiesel e glicerol | Calculada por espécie | Calculada por espécie |

A fronteira envolve exclusivamente o reator. A seta tracejada indica transferência de energia. A corrente 3 representa a mistura bruta, anterior a qualquer separação.

## 2. Descrição do processo

O triglicerídeo do óleo vegetal reage com metanol por transesterificação, formando biodiesel e glicerol. O modelo estima a produção, a sobra de reagentes e a carga térmica do reator em regime permanente.

## 3. Dados e hipóteses

| Grandeza | Valor | Unidade | Tipo |
|---|---:|---|---|
| Alimentação de TG | 800 | kg/h | Dado |
| Alimentação de metanol | 160 | kg/h | Dado |
| Massas molares (TG, metanol, biodiesel, glicerol) | 884, 32, 296, 92 | kg/kmol | Dado |
| Temperaturas das alimentações | 25 | °C | Dado |
| Temperatura do reator na base | 60 | °C | Dado |
| Conversão de TG na base, $X_{\mathrm{TG}}$ | 75 | % | Dado |
| Calor específico médio, $c_p$ | 2,5 | kJ/(kg·K) | Dado da ficha |
| Entalpia padrão da reação, $\Delta H_r^\circ$ | Desprezível, representada por 0 | kJ/kmol de reação | Hipótese da ficha |
| Pressão de operação | Suficiente para manter o metanol líquido | Condição qualitativa | Hipótese da ficha |
| Temperatura de referência para entalpia | 25 | °C | Hipótese comum |
| Temperatura de saída | Igual à do reator | °C | Hipótese comum |
| Vazões molares de TG, metanol, biodiesel e glicerol na saída | A determinar | kmol/h | 4 incógnitas |
| Taxa de avanço, $\dot\xi$ | A determinar | kmol de reação/h | 1 incógnita |
| Taxa líquida de calor, $\dot Q$ | A determinar | kJ/h | 1 incógnita energética |

**Hipóteses comuns da issue.** Regime permanente, uma reação sem reações paralelas, saída na temperatura do reator, referência de entalpia de 25 °C e pressão fora do cálculo dos balanços.

| Hipótese específica ou adicional | Justificativa no modelo |
|---|---|
| Representar o óleo por um único pseudocomponente TG | Permite converter a alimentação em base molar usando 884 kg/kmol, conforme a ficha. |
| Considerar duas alimentações sem produtos e uma saída de mistura | A ficha especifica os dois reagentes alimentados. Como a fronteira envolve apenas o reator, não há separação ou reciclo dentro do volume de controle. |
| Tratar o calor específico médio como constante | A ficha fornece um valor global e não fornece valores individuais ou curvas em função da temperatura. |
| Desprezar trabalho de eixo e variações de energia cinética e potencial | Não há dados de potência mecânica, velocidade ou desnível. A carga térmica é calculada pela variação de entalpia. |
| Desprezar perdas de calor separadas para o ambiente | A ficha não fornece dados de isolamento. Estima-se a carga térmica do modelo, sem margem de equipamento. |
| Desprezar entalpia de reação e calor de mudança de fase | Usa-se a hipótese de entalpia de reação desprezível e a condição de metanol líquido também a 70 °C. |

**Conversão da alimentação.** Divide-se a vazão mássica pela massa molar:

$$
\dot n_{\mathrm{TG},e}=\frac{800\ \mathrm{kg/h}}{884\ \mathrm{kg/kmol}}=0{,}904977\ \mathrm{kmol/h},
\qquad
\dot n_{\mathrm{MeOH},e}=\frac{160}{32}=5{,}000000\ \mathrm{kmol/h}.
$$

**Limitante e excesso.** A reação exige 3 kmol de metanol por kmol de TG. A alimentação permite avançar $0{,}904977/1=0{,}904977$ kmol/h pelo TG e $5/3=1{,}666667$ kmol/h pelo metanol. O menor valor vem do TG, portanto ele é o limitante. Para reagir todo o TG seriam necessários $3(800/884)=2{,}714932$ kmol/h de metanol. O excesso alimentado é

$$
5-2{,}714932=2{,}285068\ \mathrm{kmol/h}=73{,}12\ \mathrm{kg/h},
\qquad
100\frac{2{,}285068}{2{,}714932}=84{,}17\%.
$$

A razão molar de alimentação metanol/TG é 5,525:1, contra 3:1 na reação. O excesso de metanol pode favorecer a formação de ésteres no equilíbrio. A conversão é uma entrada fornecida pela ficha. O modelo não quantifica quanto a conversão mudaria se a alimentação de metanol fosse alterada.

## 4. Grau de liberdade (GL)

| Escopo | Incógnitas | Equações independentes | GL |
|---|---|---|---:|
| Material | Quatro vazões molares de saída e $\dot\xi$ | Quatro balanços de espécie e uma especificação de conversão | $5-5=0$ |
| Material e energia | As cinco anteriores e $\dot Q$ | As cinco anteriores e o balanço de energia, com temperatura de saída prescrita | $6-6=0$ |

A conversão fixa $\dot\xi$. Com o avanço definido, cada balanço determina a vazão de uma espécie. O balanço de energia determina $\dot Q$. O balanço global de massa decorre dos balanços por espécie multiplicados pelas massas molares, porque $\sum_i M_i\nu_i=0$. Usa-se esse balanço global para verificar os resultados.

## 5. Balanço de massa

### Equações antes da substituição — Aula 06

Em regime permanente, $\dot n_{i,s}=\dot n_{i,e}+\nu_i\dot\xi$. Sem biodiesel ou glicerol na alimentação:

$$
\begin{aligned}
\dot n_{\mathrm{TG},s}&=\dot n_{\mathrm{TG},e}-\dot\xi,\\
\dot n_{\mathrm{MeOH},s}&=\dot n_{\mathrm{MeOH},e}-3\dot\xi,\\
\dot n_{\mathrm{B},s}&=3\dot\xi,\\
\dot n_{\mathrm{G},s}&=\dot\xi,\qquad
\dot\xi=X_{\mathrm{TG}}\dot n_{\mathrm{TG},e}.
\end{aligned}
$$

### Resultados calculados — Aula 07

No caso-base, $\dot\xi=0{,}75(800/884)=0{,}678733$ kmol/h. Substitui-se nas equações e calcula-se $\dot m_{i,s}=\dot n_{i,s}M_i$.

| Espécie | Balanço molar na saída | Saída (kmol/h) | Saída (kg/h) |
|---|---|---:|---:|
| TG | $0{,}904977-\dot\xi$ | 0,226244 | 200,0000 |
| Metanol | $5-3\dot\xi$ | 2,963801 | 94,8416 |
| Biodiesel | $3\dot\xi$ | 2,036199 | 602,7149 |
| Glicerol | $\dot\xi$ | 0,678733 | 62,4434 |
| **Total com precisão de cálculo** | | **5,904977** | **960,0000** |

Exemplo para o biodiesel, usando o avanço sem arredondar:

$$
\dot m_{\mathrm B,s}=3\left(0{,}75\,\frac{800}{884}\right)(296)
=602{,}7149\ \mathrm{kg/h}.
$$

## 6. Sistema reativo e estequiometria

**Reação:** TG + 3 CH₃OH → 3 B + G.

| Espécie | $\nu_i$ | Interpretação por kmol de avanço |
|---|---:|---|
| TG | −1 | Consome 1 kmol |
| Metanol | −3 | Consome 3 kmol |
| Biodiesel (B) | +3 | Forma 3 kmol |
| Glicerol (G) | +1 | Forma 1 kmol |

Na base, o consumo de TG é 0,678733 kmol/h e o de metanol é 2,036199 kmol/h. Formam-se 2,036199 kmol/h de biodiesel e 0,678733 kmol/h de glicerol. A conversão se recupera por $(0{,}904977-0{,}226244)/0{,}904977\simeq75\%$.

**Quanto metanol sobra?** Há **73,12 kg/h de excesso estequiométrico alimentado** em relação à conversão total do TG. Como a conversão prescrita é de 75%, **94,84 kg/h saem sem reagir**. A diferença de 21,72 kg/h é o metanol que seria consumido para reagir os 200 kg/h restantes de TG. A recuperação desse metanol é uma possibilidade a jusante, fora da fronteira do modelo.

## 7. Balanço de energia

Consideram-se as entalpias sensíveis das alimentações e da saída e a entalpia de reação. A referência é 25 °C e o calor é positivo para aquecimento:

$$
\dot Q=
\underbrace{\sum_s\dot m_s c_p(T_s-T_{\mathrm{ref}})}_{\text{entalpia sensível de saída}}
-\underbrace{\sum_e\dot m_e c_p(T_e-T_{\mathrm{ref}})}_{\text{entalpia sensível de entrada}}
+\underbrace{\dot\xi\Delta H_r^\circ}_{\text{termo reacional}}.
$$

Na base, as entradas estão na referência, o termo reacional é nulo por hipótese e a massa de saída é 960 kg/h. Assim:

$$
\dot Q=(960\ \mathrm{kg/h})[2{,}5\ \mathrm{kJ/(kg\,K)}](35\ \mathrm K)
=84\,000\ \mathrm{kJ/h}
=\frac{84\,000}{3\,600}\ \mathrm{kW}=23{,}33\ \mathrm{kW}.
$$

A unidade é kJ/h porque vazão mássica, calor específico e diferença de temperatura foram expressos em kg/h, kJ/(kg·K) e K. A carga positiva exige aporte de calor nas condições propostas.

## 8. Modelo em Python e Google Colab

- [Aula 06 — modelo v1, com sete células de títulos e dados](Biodiesel_Aula06_Modelo_v1.ipynb).
- [Aula 07 — modelo calculado, com sete células executáveis](Biodiesel_Aula07_Modelo_Calculado.ipynb).

As células seguem a sequência pedida: Dados → Conversão de unidades → Estequiometria → Balanços de massa → Balanço de energia → Validação → Cenários. Abra o notebook calculado no Colab e use **Ambiente de execução → Executar tudo**. O modelo calcula com a precisão interna do Python e arredonda somente a exibição.

## 9. Validação

**Teste escolhido no modelo v1.** Somar as vazões mássicas de saída antes de arredondá-las e verificar que $\lvert\dot m_s-\dot m_e\rvert\leq10^{-6}$ kg/h. O notebook verifica também estequiometria, vazões não negativas, conversão recalculada, avanço admissível e coerência do total molar.

| Verificação | Resultado na condição-base |
|---|---|
| Massa da reação | $884+3(32)=3(296)+92=980$ kg por kmol de reação |
| Massa total | Entrada = 960 kg/h e saída = 960 kg/h com a precisão do cálculo. Erro relativo numérico de aproximadamente 0%. |
| Soma exibida a duas casas | $200{,}00+94{,}84+602{,}71+62{,}44=959{,}99$ kg/h. A diferença de 0,01 kg/h é de apresentação. |
| Avanço e conversão | $0\leq0{,}678733\leq0{,}904977$ kmol/h, com conversão recalculada de 75%. |
| Total molar | $\sum_i\nu_i=-1-3+3+1=0$. A entrada e a saída totalizam 5,904977 kmol/h. A igualdade resulta desta reação particular. |

Conservação de massa, não negatividade e fechamento dos balanços demonstram consistência interna. Para confirmar desempenho industrial seriam necessários dados de equilíbrio ou cinética, condições reais de fase e perdas de calor.

## 10. Análise dos dois cenários

Nas duas comparações, uma variável por vez é modificada conforme os valores indicados na ficha. As alimentações permanecem em 800 kg/h de TG e 160 kg/h de metanol.

| Resultado | Unidade | Base | Cenário 1 · Conversão | Cenário 2 · Temperatura | Combinado · Complementar |
|---|---|---:|---:|---:|---:|
| Conversão de TG | % | 75 | 85 | 75 | 85 |
| Temperatura do reator | °C | 60 | 60 | 70 | 70 |
| Taxa de avanço | kmol/h | 0,678733 | 0,769231 | 0,678733 | 0,769231 |
| TG na saída | kg/h | 200,00 | 120,00 | 200,00 | 120,00 |
| Metanol na saída | kg/h | 94,84 | 86,15 | 94,84 | 86,15 |
| Biodiesel produzido | kg/h | 602,71 | 683,08 | 602,71 | 683,08 |
| Glicerol produzido | kg/h | 62,44 | 70,77 | 62,44 | 70,77 |
| Calor líquido | kJ/h | 84.000 | 84.000 | 108.000 | 108.000 |
| Potência térmica | kW | 23,33 | 23,33 | 30,00 | 30,00 |

- **Cenário 1.** $\dot\xi=0{,}85(800/884)=0{,}769231$ kmol/h e $\dot m_B=3(0{,}85)(800/884)(296)=683{,}08$ kg/h. O ganho calculado antes do arredondamento é de **80,36 kg/h** (+13,33%). Como temperatura, vazão total e $c_p$ permanecem iguais e a entalpia de reação é desprezível, o calor calculado continua em 23,33 kW.
- **Cenário 2.** $\dot Q=960(2{,}5)(70-25)=108\,000$ kJ/h, ou **30,00 kW** (+6,67 kW ou 28,57%). As vazões por espécie permanecem iguais porque a conversão continua fixada em 75%. Na análise a 70 °C, mantém-se a hipótese de pressão suficiente para o metanol permanecer líquido.
- **Combinado.** Com as duas alterações, o modelo dá 683,08 kg/h e 30,00 kW. Conversão e temperatura são especificações independentes. A conversão atingível a 70 °C exigiria um estudo de cinética e equilíbrio.

## 11. Conclusão

Na base, a unidade produz **602,71 kg/h de biodiesel** e **62,44 kg/h de glicerol** na mistura do reator. O TG é limitante. A alimentação contém **73,12 kg/h de metanol em excesso estequiométrico** e a corrente de saída contém **94,84 kg/h de metanol não reagido**. A condição-base requer **23,33 kW de aquecimento**. Atingir 85% eleva a produção para **683,08 kg/h** e operar a 70 °C eleva a demanda de aquecimento para **30,00 kW**. A avaliação da capacidade de operar nesses pontos depende de confirmar reação, fase e perdas térmicas.

## 12. Roteiro de apresentação — aproximadamente 10 min

| Tempo | Sugestão de divisão | O que mostrar |
|---|---|---|
| 0:00–2:00 | Gustavo | Pergunta do gerente, reação, fluxograma e fronteira. |
| 2:00–4:30 | Gustavo | Base molar, limitante, o significado dos 73,12 kg/h e tabela do GL. |
| 4:30–7:00 | Jorge | Avanço, vazões de saída e balanço térmico com a conversão kJ/h → kW. |
| 7:00–9:00 | Jorge | Notebook, validação e tabela dos dois cenários. |
| 9:00–10:00 | Ambos | Resposta ao gerente e limites do modelo. |

Cada integrante deve conseguir explicar como reproduzir os 602,71 kg/h, por que o calor é positivo, por que o balanço global serve como teste e de onde vêm os 94,84 kg/h de metanol remanescente.

## Apêndice — revisão e conferência da entrega

| Item da issue | O que já existia | Revisão concluída |
|---|---|---|
| Aula 06 · processo, hipóteses e fluxograma | Descrição, hipóteses e correntes no texto. A fronteira era descrita em palavras. | Descrição curta, fronteira desenhada e três correntes de matéria numeradas com espécies e unidades. |
| Aula 06 · dados, incógnitas e GL | Dados e incógnitas em listas separadas e GL de material correto. | Classificação em tabela única, GL de material mantido e GL de energia justificado como extensão. |
| Aula 06 · equações e teste | Relação geral de balanço, conversão e teste de massa. O notebook original já estava calculado. | Equações sem substituição em seção própria, termos de energia explícitos e versão v1 em sete células. |
| Aula 07 · balanços e código | Balanços corretos na base e notebook com saídas calculadas. A introdução do Colab dizia que havia uma só alimentação. O código também chamava °C de escala absoluta. | Duas alimentações em ambos os arquivos, convenção de unidades corrigida e sete células executáveis. |
| Aula 07 · cenários e validação | O Colab original já testava os dois efeitos isolados e o caso combinado. O relatório só mostrava base e combinado. A validação do texto atribuía 960 kg/h à soma arredondada. | Relatório alinhado ao Colab, sensibilidade por variável e arredondamento de 959,99 kg/h explicitado. |
| Aula 08 · conclusão e apresentação | Conclusão já redigida. Roteiro de 10 min ausente no material consultado. | Conclusão quantitativa e roteiro de 10 min para a dupla. |

**Entrega da Aula 06.** A issue solicita foto do fluxograma e da tabela de GL, além do link do notebook no ambiente da turma. O fluxograma e a tabela acima podem ser reproduzidos para a foto. Depois de importar o modelo v1 no Colab, a dupla pode compartilhar o link com o professor no ambiente da turma. A foto, a postagem e a apresentação fazem parte da entrega da dupla.

**Fontes do projeto**

- [Issue #24 — PBL Final, ficha técnica da Dupla 02 e critérios de entrega](https://github.com/evertonesaa/Principios-e-Calculos-da-Engenharia/issues/24).
- [Relatório original da dupla — PROJETO INTEGRADOR](https://github.com/guuhxr/PCEEEEE/blob/main/PROJETO%20INTEGRADOR).
- [Notebook original da dupla — Colab_Relação_de_Biodiesel](https://colab.research.google.com/drive/1-3z60yxps-cLY2Xf733yIRNog0o3BrL7?usp=sharing).
