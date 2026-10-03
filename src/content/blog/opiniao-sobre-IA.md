---
title: 'Qual a minha opinião sobre a área de IA?'
description: 'Percepção e opinião sobre a área de IA.'
pubDate: '2026-10-03'
---

Desde o fim de 2022 existe uma crescente demanda por soluções de inteligência artificial. As LLMs vieram
para mudar a forma como interagimos com a tecnologia. Porém, mesmo com o avanço tecnológico, na minha 
visão ela também trouxe preocupações que acho importante pontuar.

Antes de entrar no tema, existem alguns pontos que gostaria de destacar. Nesse blog a minha ideia é
escrever com minhas próprias palavras, não vou usar IA para gerar o conteúdo. E não, não sou hater de IA.
Eu uso todos os dias e acho fantástico, mas na minha percepção o fato de terceirizar a escrita de artigos é prejudicial.
A organização de ideias, raciocínio e tomada de decisão precisam estar no meu controle.

---

## 1. LLMs

Vamos lá... não tem como negar que essa tecnologia é sensacional. É impressionante a velocidade que conseguimos
validar ideias e implementar soluções com ela. Portanto, não tem como negar que elas vieram para ficar. Temos que nos
adaptar e utilizá-la de forma responsável, fazendo com que ela amplifique nosso conhecimento.

Se colocarmos a LLM na mão de um profissional que tem muita bagagem profissional e comparar os resultados com outro profissional que não tem essa bagagem, com toda certeza teremos uma discrepância enorme nos resultados.

---

## 2. LLMs sabem qual é o melhor caminho?

O primeiro ponto que precisamos pontuar sobre essa tecnologia é que ela é probabilística. O objetivo dela é gerar o próximo token. Ela não sabe o que está fazendo, e é exatamente por isso que ela precisa de bons profissionais para pilotá-la. Para ficar mais claro, vamos para um exemplo:

- Suponha que você precisa implementar uma solução para realizar ingestão de documentos em um sistema de busca. Com uma linha a LLM com toda certeza vai gerar o template de ingestão de documentos: `Crie um projeto onde eu consiga fazer a ingestão de documentos em uma base vetorial e depois consiga testar a busca`.

Ótimo, agora que temos o template. Mas ela vai gerar a ingestão com características que ela achou que seriam importantes dada a probabilidade de sucesso. Mas e aí? Qual estratégia de chunking (divisão dos documentos) é importante para os seus dados? Só um split por algum caractere já resolve? Ela sabe dessas necessidades específicas?

Uma das coisas que mais tenho visto são casos onde pedidos genéricos são feitos, a LLM gera respostas probabilísticas e o usuário aceita como o melhor caminho. Isso tem custo a curto, médio e longo prazo. Se você não especificar, ela vai decidir por você. Se você não conhece o que está pedindo, você deveria assumir responsabilidade e autoria dessa solução?

E não, não tô sendo radical e falando que a LLM não consegue oferecer possibilidades boas. Ela consegue. E acho super válido trocar ideia com ela. Muitas vezes antes de desenhar alguma solução, eu troquei uma ideia com ela antes e tomei minha decisão. Mas já cheguei com um plano pronto e especifiquei pra ela.

---

## 3. Aplicação em domínios errados

Outro ponto que vale a pena destacar é que LLMs estão sendo usadas para casos onde técnicas mais simples resolvem de forma mais barata e eficiente. Por exemplo:

- LLMs não sabem analisar dados. Devo pedir pra LLM analisar um dado? Não. Preciso fornecer ferramentas para que ela use e interprete as saídas.
- Preciso capturar um padrão em um texto. Será que `regex` já não me atenderia? Já vi muitos casos onde escolheram usar LLM.

Precisamos ter o raciocínio crítico para entender quando usar uma técnica simples e quando usar uma LLM.

---

## 4. Confiança em algo probabilístico

Devo confiar em algo probabilístico? Sim, se eu souber o que estou fazendo e se eu souber medir o que estou pedindo.

Se você gera código, a confiança não vem de achar que o modelo acertou de primeira, mas sim de ter testes automatizados, checagem de tipos e validação criteriosa do que foi gerado. Se você constrói pipelines com LLMs, precisa de validações de schema, métricas claras e rotinas de avaliação (*evals*). Confiança em sistemas probabilísticos não é fé cega na saída do modelo: é a nossa capacidade técnica de cercar essa saída com garantias determinísticas.

---

## Conclusão

E novamente, eu uso muito LLMs no dia a dia... acho que deve ter alguns meses que não programo manualmente. Portanto, não estou aqui para pregar contra o uso delas. Na verdade, acho que elas são uma ferramenta poderosa que merece ser usada com sabedoria. E que devemos investir cada vez mais em dominar os conceitos para usar elas com eficiência.
