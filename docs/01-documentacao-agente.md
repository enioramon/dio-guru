# Guru — Agente Financeiro

## Caso de uso
O Guru é um agente financeiro para relacionamento com o cliente que:
1) entende perguntas em linguagem natural,
2) consulta uma base de conhecimento (perfil, transações, histórico de atendimento e produtos),
3) retorna respostas contextualizadas e simulações simples (metas e reserva),
4) recomenda produtos compatíveis com o perfil e com o objetivo.

Exemplos do que o Guru resolve:
- “Quanto falta para completar minha reserva de emergência?”
- “Quanto preciso guardar por mês até 2026-06?”
- “Quais produtos combinam com meu perfil moderado e foco em reserva?”
- “Me explique Tesouro Selic e CDB liquidez diária.”

## Persona e tom de voz
- Persona: “consultor financeiro didático e prudente”
- Tom: claro, objetivo, sem jargão desnecessário, educado e cuidadoso com risco.
- Postura: não promete rentabilidade, não dá recomendação absoluta, sempre apresenta ressalvas.

## Arquitetura (visão simples)
Entrada (usuário) -> Interpretação (regras + LLM opcional) ->
Consulta à base local (CSV/JSON) -> Cálculos determinísticos ->
Resposta (com fontes internas e avisos de segurança)

Componentes:
- Loader de dados (CSV/JSON)
- Funções de análise (resumo de gastos / metas)
- Recomendador de produtos (filtro por risco e objetivo)
- Camada de segurança (anti-alucinação)
- UI (Streamlit)

## Segurança e anti-alucinação
Regras:
1) O Guru só afirma fatos sobre cliente/produtos se estiverem na base local.
2) Se faltar dado: responde explicitamente “não tenho essa informação na minha base”.
3) Para cálculos: usa funções determinísticas (Python) e mostra conta/resumo.
4) Para explicações: limita-se ao catálogo de produtos e conceitos gerais (sem prometer retorno).
5) Inclui avisos: “conteúdo educacional, não é recomendação financeira formal”.
