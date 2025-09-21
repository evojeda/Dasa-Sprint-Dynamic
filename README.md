# Relatório – Estruturas de Dados e Algoritmos para Solução empresa Dasa

O desafio apresentado nas unidades de diagnóstico da **Dasa** evidencia a dificuldade em registrar com precisão o consumo diário de insumos, como reagentes e descartáveis. Essa falha compromete tanto o controle de estoque quanto a previsão de reposição.
Para enfrentar esse problema, implementamos diferentes estruturas de dados e algoritmos clássicos que simulam o registro, a consulta e a organização das informações de consumo. A seguir, detalhamos como cada técnica foi aplicada no contexto do problema.

---

### 1. Fila (FIFO)

A fila, que segue a lógica *First In, First Out*, foi usada para registrar o consumo dos insumos em ordem cronológica.
Cada retirada feita pelos colaboradores é enfileirada, garantindo que os registros mantenham a mesma ordem em que ocorreram no dia. Isso é essencial porque preserva a sequência dos eventos, evitando confusão em relatórios ou distorções na análise de movimentação de estoque.
No contexto da Dasa, a fila ajuda a reproduzir fielmente o histórico de consumos: o primeiro insumo retirado será o primeiro processado, o que apoia tanto a rastreabilidade quanto a auditoria.

---

### 2. Pilha (LIFO)

A pilha, que segue a lógica *Last In, First Out*, foi implementada para consultas em ordem inversa.
Enquanto a fila privilegia a ordem cronológica, a pilha permite acessar primeiro os consumos mais recentes, algo extremamente útil para gestores ou auditores que precisam verificar rapidamente o que foi retirado por último.
No caso da Dasa, isso facilita, por exemplo, verificar movimentações anormais ocorridas no final do dia ou analisar o impacto imediato de consumos inesperados.

---

### 3. Busca Sequencial

A busca sequencial percorre a lista de insumos até encontrar o item desejado. Embora seja um algoritmo simples e com custo linear (*O(n)*), ele é eficaz em situações com poucos registros ou quando não há necessidade de ordenação prévia.
No contexto do problema, a busca sequencial permite localizar de forma prática um insumo específico entre os registros de consumo do dia. Mesmo que não seja a opção mais rápida, atende bem à realidade de listas pequenas, como retiradas registradas em um único turno.

---

### 4. Busca Binária

A busca binária, por sua vez, requer que a lista esteja ordenada, mas em troca garante um desempenho muito superior (*O(log n)*).
No projeto, ela foi aplicada sobre listas de insumos organizadas alfabeticamente. Essa abordagem possibilita localizar rapidamente um insumo específico, reduzindo o número de comparações necessárias.
Para a Dasa, isso é útil em relatórios maiores, onde há centenas de registros de insumos. Nesses casos, a busca binária proporciona agilidade, evitando que o gestor precise percorrer todos os dados.

---

### 5. Merge Sort

O algoritmo **Merge Sort** foi utilizado para ordenar os insumos por **quantidade consumida**. Essa ordenação é estratégica, pois permite identificar rapidamente quais insumos tiveram maior saída e, portanto, demandam reposição urgente.
O Merge Sort garante estabilidade e eficiência mesmo em listas extensas (*O(n log n)*), o que o torna ideal para lidar com grandes volumes de dados.
Aplicado à realidade da Dasa, ele apoia diretamente o planejamento de compras e o controle de estoque, evitando rupturas em insumos críticos.

---

### 6. Quick Sort

O **Quick Sort** foi aplicado para ordenar os insumos pela **validade**. Essa ordenação segue o princípio FEFO (*First Expire, First Out*), priorizando o uso dos insumos que vencem primeiro.
Ao organizar o estoque dessa forma, reduz-se o risco de desperdícios por vencimento, o que gera economia e maior eficiência operacional.
Embora o Quick Sort tenha como pior caso o custo *O(n²)*, na prática ele costuma ser rápido e eficiente, especialmente em dados moderados como os do nosso exemplo.
Para a Dasa, essa aplicação garante que insumos de validade próxima sejam usados antes dos demais, minimizando perdas e garantindo a qualidade do atendimento.

---

## Conclusão

Essas técnicas, embora simples e didáticas, se conectam diretamente à realidade da Dasa, mostrando como a **lógica computacional** pode melhorar processos do dia a dia, aumentar a rastreabilidade e dar suporte à tomada de decisão.
