# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Resposta obtida:** Não somou todos os gastos com alimentação, informou apenas um.
- **Resultado:** [ ] Correto  [X] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Resposta obtida:** Responde perfeitamente, baseando-se no perfil do cliente
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resposta obtida:** Acerta em partes, ele não falou de assuntos fora do escopo, mas na mesma resposta trouxe informações equivocadas. 
- **Resultado:** [ ] Correto  [X] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o BBDC3 na Bovespa?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resposta obtida:** Ele diz que não é um especialista no assunto e não pode informar a rentabilidade, mas tenta explicar o que é o BBDC3 e passa informações equivocadas.
- **Resultado:** [ ] Correto  [X] Incorreto

---

## Resultados

Baseando-se nas perguntas e respostas pode-se concluir que o chat-bot consegue até dar algumas respostas corretas, mas quando ele aprofunda um pouco mais na resposta acaba se perdendo, resultando em informações equivocadas. Quando precisava buscar informações que ja tinha, como por exemplo a do arquivo transacoes.csv, ele tambem errava, ignorando algumas informações contidas no arquivo.

**O que pode melhorar:**
- O modelo de linguagem artificial usado para o chat bot foi o mistral, por ser mais leve, para qua minha máquina suporte. Por isso muitas vezes o chat-bot quando exigido da informações equivocadas. Se utilizarmos o gpt-oss, que possui mais parâmetros, mais eficiência, as respostas seriam muito mais precisas, mas no momento atual minha máquina infelizmente não tem capacidade para trabalhar com ele.
