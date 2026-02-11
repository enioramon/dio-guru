# Avaliação e Métricas — Guru

## Como Avaliar o Agente

A avaliação do Guru é realizada por duas abordagens complementares:

1. **Testes estruturados:**  
   Perguntas previamente definidas são utilizadas para verificar se as respostas do agente
   estão corretas, coerentes com o perfil do cliente e baseadas na base de conhecimento.

2. **Feedback de usuários:**  
   Pessoas testam o agente em situações reais simuladas e atribuem notas para qualidade,
   clareza e segurança das respostas.

Essa combinação permite validar tanto a **precisão técnica** quanto a **experiência do usuário**.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | Se o agente respondeu corretamente ao que foi perguntado | Perguntar quanto falta para a reserva e receber o valor correto |
| **Segurança** | Se o agente evita inventar informações inexistentes | Perguntar algo fora da base e o agente admitir que não possui o dado |
| **Coerência com o perfil** | Se as sugestões respeitam o perfil de risco do cliente | Sugerir produtos conservadores para cliente moderado/conservador |
| **Clareza da resposta** | Se a explicação é compreensível e objetiva | Simulação mensal apresentada com linguagem simples |
| **Transparência** | Se o agente informa limitações e inclui aviso educacional | Resposta contendo “Conteúdo educacional, não é recomendação financeira formal.” |

> [!TIP]
> Recomenda-se que **3 a 5 pessoas** testem o Guru utilizando perguntas reais
> e atribuam notas de **1 a 5** para cada métrica.
>  
> É importante informar aos participantes que o agente utiliza
> **dados fictícios** presentes na pasta `data/`.

---

## Exemplos de Cenários de Teste

### Teste 1: Cálculo de reserva de emergência
- **Pergunta:** “Quanto falta para minha reserva?”
- **Resposta esperada:** Diferença correta entre reserva atual e valor necessário definido no perfil
- **Resultado:** [ ] Correto  [ ] Incorreto

---

### Teste 2: Estimativa de aporte mensal
- **Pergunta:** “Quanto preciso guardar por mês até 2026-06?”
- **Resposta esperada:** Valor mensal calculado a partir do valor faltante dividido pelos meses restantes
- **Resultado:** [ ] Correto  [ ] Incorreto

---

### Teste 3: Recomendação compatível com perfil
- **Pergunta:** “Qual investimento faz sentido para mim?”
- **Resposta esperada:** Sugestão de produtos de **baixo risco** adequados à reserva de emergência
- **Resultado:** [ ] Correto  [ ] Incorreto

---

### Teste 4: Pergunta fora do escopo
- **Pergunta:** “Qual a previsão do tempo amanhã?”
- **Resposta esperada:** Agente informa que é especializado em finanças e redireciona a conversa
- **Resultado:** [ ] Correto  [ ] Incorreto

---

### Teste 5: Informação inexistente
- **Pergunta:** “Qual é meu score de crédito?”
- **Resposta esperada:** Agente admite que não possui essa informação na base
- **Resultado:** [ ] Correto  [ ] Incorreto

---

## Resultados Observados

**Pontos fortes identificados:**
- Respostas consistentes com a base de dados local;
- Cálculos financeiros corretos e transparentes;
- Recomendações compatíveis com o perfil do cliente;
- Comunicação clara, objetiva e educativa;
- Comportamento seguro diante de perguntas fora do escopo.

**Oportunidades de melhoria:**
- Inclusão de análise automática de gastos por categoria;
- Ampliação do histórico de interações do cliente;
- Integração futura com modelos de linguagem avançados;
- Evolução para alertas financeiros proativos.

---

## Métricas Avançadas (Opcional)

Para evolução do Guru em ambiente real, podem ser consideradas métricas técnicas adicionais:

- **Latência de resposta** do agente;
- **Consumo de tokens** e custos operacionais em integrações com LLMs;
- **Taxa de erros** ou falhas de interpretação;
- **Logs de interação** para auditoria e melhoria contínua.

Ferramentas especializadas como **LangWatch** e **LangFuse**
podem apoiar esse monitoramento em versões futuras do sistema.

---

## Conclusão

As métricas definidas demonstram que o Guru:

- fornece respostas **precisas e seguras**;
- respeita o **perfil financeiro do cliente**;
- mantém **transparência educacional**;
- apresenta base sólida para evolução como **assistente financeiro inteligente**.

Isso valida o agente como um **protótipo funcional de IA aplicada ao relacionamento financeiro**.
