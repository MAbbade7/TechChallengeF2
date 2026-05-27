# 🎬 Roteiro — Vídeo Executivo (até 5 minutos)

## Classificação da Qualidade de Vinhos com Machine Learning

> **Dica:** Linguagem executiva — imagine que está apresentando para diretores de uma vinícola. Evite termos técnicos.

---

## ⏱️ 0:00 – 0:30 | Abertura

**[Apresentador na tela ou slide de capa]**

> "Olá! Somos o grupo formado por Marcelo Abbade, André Vieira, Lívia De Oliveira, Allan Diniz e Matheus Gueicha, alunos da Pós-Graduação em Data Analytics da FIAP/POS TECH."
>
> "Hoje vamos apresentar nosso projeto do Tech Challenge Fase 2: como usar dados para prever a qualidade de um vinho — antes mesmo de ele ser avaliado por um especialista."

---

## ⏱️ 0:30 – 1:15 | O Problema

**[Slide: O Desafio]**

> "A indústria de vinhos avalia a qualidade dos seus produtos por meio de degustadores especialistas. Esse processo é demorado, subjetivo e depende da experiência de cada avaliador."
>
> "Nossa pergunta foi: **será que conseguimos prever se um vinho é de alta qualidade usando apenas dados da sua composição química?**"
>
> "Para isso, analisamos um banco de dados público com quase 1.600 amostras de vinho tinto, contendo 11 características como teor alcoólico, acidez e níveis de enxofre."

---

## ⏱️ 1:15 – 2:15 | O que os Dados nos Contaram

**[Slide: Análise dos Dados / Correlações]**

> "Primeiro, exploramos os dados para entender o que diferencia um vinho bom de um vinho mediano."
>
> "Descobrimos que apenas **13,6% dos vinhos** da base são de alta qualidade — ou seja, é um produto raro, o que torna a previsão mais desafiadora."
>
> "As análises revelaram padrões claros:"
>
> - "**Vinhos com maior teor alcoólico** tendem a ter qualidade superior"
> - "**Acidez volátil alta** é um sinal negativo — está associada a sabores desagradáveis como vinagre"
> - "**Sulfatos em níveis adequados** contribuem para a preservação e qualidade"
> - "**Ácido cítrico** em boa quantidade traz frescor ao vinho"
>
> "Também identificamos valores extremos em algumas variáveis, como cloretos e açúcar residual, que precisaram de tratamento especial."

---

## ⏱️ 2:15 – 3:15 | A Solução

**[Slide: Metodologia / Resultados]**

> "Com esses insights, construímos três modelos de inteligência artificial para prever automaticamente a qualidade do vinho."
>
> "Antes de treinar os modelos, preparamos os dados: padronizamos as escalas, criamos novas variáveis combinando características existentes, e equilibramos a base para que o modelo aprendesse igualmente sobre vinhos bons e medianos."
>
> "Testamos três abordagens diferentes e a que apresentou melhor resultado foi a **Regressão Logística**, com uma taxa de acerto de 90% na capacidade de distinguir vinhos de alta e baixa qualidade."

---

## ⏱️ 3:15 – 4:15 | Resultados e Recomendações

**[Slide: Recomendações para Produção]**

> "O que isso significa na prática para uma vinícola?"
>
> "Nosso modelo identificou as **4 alavancas principais** que um produtor pode monitorar:"
>
> 1. "**Teor alcoólico** — otimizar o processo de fermentação para atingir níveis ideais"
> 2. "**Acidez volátil** — controlar rigorosamente para evitar degradação do sabor"
> 3. "**Sulfatos** — ajustar os níveis para melhor preservação"
> 4. "**Ácido cítrico** — manter em quantidade adequada para equilíbrio e frescor"
>
> "Com esse modelo, um produtor pode analisar a composição do vinho **durante a produção** e fazer ajustes antes da avaliação final — economizando tempo e reduzindo a subjetividade."

---

## ⏱️ 4:15 – 5:00 | Conclusão

**[Slide: Conclusão]**

> "Em resumo: analisamos quase 1.600 vinhos, identificamos os fatores-chave de qualidade e construímos um modelo com 90% de capacidade de acerto."
>
> "Isso mostra que a ciência de dados pode ser uma aliada poderosa para a indústria vitivinícola — transformando dados em decisões mais inteligentes e produtos de melhor qualidade."
>
> "Obrigado pela atenção! O código completo e a análise detalhada estão disponíveis no nosso repositório no GitHub."

---

## 📋 Dicas para a Gravação

- **Duração:** Máximo 5 minutos — ensaie antes para não estourar
- **Linguagem:** Executiva, sem jargões técnicos (não fale "SMOTE", "AUC-ROC", "StandardScaler")
- **Visual:** Use a apresentação HTML como slides de fundo (abra no Chrome em tela cheia com F11)
- **Divisão sugerida:** Um ou dois integrantes apresentam, os demais aparecem na abertura/encerramento
- **Ferramenta:** Grave pelo Google Meet, Zoom ou Loom (compartilhando tela com os slides)
