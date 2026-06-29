# 🎬 Roteiro do Vídeo Executivo — Tech Challenge Fase 2

**Duração total:** até 5 minutos
**Tom:** Executivo, linguagem acessível, como se apresentasse para diretores
**Suporte visual:** Apresentação HTML (`docs/apresentacao_executiva.html`)

---

## 📋 Abertura (0:00 – 0:30) — *Slide 1*

> "Olá! Somos **Marcelo Abbade** (RM373613), **André Vieira** (RM370784), **Lívia De Oliveira** (RM370348), **Allan Diniz** (RM373478) e **Matheus Gueicha** (RM371344), alunos da Pós-Graduação em Data Analytics da FIAP.
>
> Hoje vamos apresentar nosso projeto do Tech Challenge Fase 2: como usamos **inteligência artificial para prever a qualidade de vinhos** — transformando dados químicos em decisões inteligentes para a indústria vinícola."

---

## 🎯 O Problema (0:30 – 1:15) — *Slides 2 e 3*

> "Tradicionalmente, a qualidade de um vinho é avaliada por sommeliers — um processo **subjetivo, caro e difícil de escalar**.
>
> Nossa pergunta foi: **é possível prever se um vinho é de alta qualidade usando apenas suas propriedades químicas?**
>
> Trabalhamos com um dataset de **1.599 vinhos tintos portugueses**, cada um descrito por 11 variáveis químicas como teor alcoólico, acidez e sulfatos.
>
> Na fase de limpeza, identificamos que **240 registros (15%)** eram duplicatas exatas. Removemos para evitar viés no modelo — ficamos com **1.359 amostras confiáveis**."

---

## 📊 O que os Dados nos Contaram (1:15 – 2:15) — *Slides 4, 5 e 6*

> "A análise exploratória revelou descobertas importantes:
>
> **Primeiro**, o desbalanceamento: **86% dos vinhos são de qualidade baixa/média** e apenas 14% são de alta qualidade. Isso exigiu técnicas especiais de balanceamento.
>
> **Segundo**, identificamos os 3 fatores mais importantes:
> - O **teor alcoólico** é o principal preditor — vinhos melhores têm mais álcool, indicando uvas mais maduras.
> - A **acidez volátil** tem impacto negativo — excesso indica problemas na fermentação.
> - Os **sulfatos** ajudam a preservar aromas e sabores — associados a vinhos de maior qualidade.
>
> Também criamos 4 novas variáveis a partir das originais para capturar interações entre os compostos químicos."

---

## 🤖 A Solução (2:15 – 3:15) — *Slides 7 e 8*

> "Treinamos três modelos de Machine Learning:
> - **Regressão Logística** — modelo clássico e interpretável
> - **Random Forest** — conjunto de árvores de decisão
> - **Gradient Boosting** — técnica avançada de ensemble
>
> Para lidar com o desbalanceamento, aplicamos a técnica **SMOTE**, que cria exemplos sintéticos da classe minoritária — apenas nos dados de treino, para não contaminar a avaliação.
>
> O **melhor modelo foi a Regressão Logística**, com um AUC de **0.90** — ou seja, o modelo consegue distinguir corretamente um vinho de alta qualidade em **90% dos casos**.
>
> Curiosamente, o modelo mais simples superou os mais complexos — evidência de que os dados têm uma **relação linear forte** com a qualidade."

---

## 💡 Recomendações (3:15 – 4:15) — *Slide 9*

> "Com base nos resultados, três recomendações práticas para a indústria:
>
> **1. Priorizar a maturação das uvas** — vinhos de alta qualidade consistentemente têm maior teor alcoólico, que vem de uvas mais maduras.
>
> **2. Controlar rigorosamente a acidez volátil** — manter baixa é essencial. Excesso indica contaminação bacteriana durante a fermentação.
>
> **3. Monitorar os níveis de sulfatos** — em doses adequadas, são aliados na conservação de aromas e sabores que definem um bom vinho.
>
> Esse modelo pode ser usado como **ferramenta de triagem rápida** no controle de qualidade, complementando — não substituindo — a avaliação dos especialistas."

---

## 🏁 Conclusão (4:15 – 5:00) — *Slide 9*

> "Em resumo: analisamos 1.359 vinhos, treinamos 3 modelos e alcançamos uma **taxa de acerto de 90%** na distinção entre vinhos de alta e baixa qualidade.
>
> Demonstramos que **dados químicos objetivos podem prever qualidade** — transformando um processo historicamente subjetivo em uma decisão baseada em evidências.
>
> Obrigado! O código completo e toda a documentação estão disponíveis no nosso repositório GitHub."

---

## ⏱️ Resumo de Tempos

| Seção | Início | Duração |
|-------|--------|---------|
| Abertura | 0:00 | 30s |
| O Problema | 0:30 | 45s |
| Dados | 1:15 | 60s |
| Solução | 2:15 | 60s |
| Recomendações | 3:15 | 60s |
| Conclusão | 4:15 | 45s |
| **Total** | — | **5:00** |
