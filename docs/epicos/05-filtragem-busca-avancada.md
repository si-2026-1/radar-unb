# Épico 5: Filtragem e Busca Avançada

**Descrição:**
Com a alimentação contínua do mapa georreferenciado, a quantidade de dados visuais pode facilmente sobrecarregar a interface. Este épico foca em fornecer um motor de busca robusto e um sistema de filtros dinâmicos, permitindo que diferentes perfis da comunidade isolem informações específicas. O objetivo é garantir o rápido acesso a dados relevantes, cruzando variáveis como texto, tempo, categoria, status e proximidade espacial.

**Requisitos Funcionais Associados:** 

* RF-FIL-01, RF-FIL-02, RF-FIL-03, RF-FIL-04, RF-FIL-05, RF-FIL-06, RF-FIL-07, RF-FIL-08, RF-FIL-09

---

## Histórias de Usuário (User Stories)

**Buscar com sugestões automáticas:** Como usuário, quero digitar palavras-chave numa barra de busca e receber sugestões automáticas, para encontrar eventos específicos sem precisar navegar manualmente pelo mapa.

*  **Critérios de Aceitação:**
  - A barra de busca exibe sugestões automáticas a partir de 2 caracteres digitados (RF-FIL-04).
  - As sugestões são baseadas em títulos, descrições e tags de ocorrências e eventos.
  - Ao selecionar uma sugestão, o mapa centraliza e destaca o resultado correspondente.
  - Se não houver resultados, a interface exibe uma mensagem indicando que nenhum item foi encontrado.

**Filtrar por faixa de datas e tipo:** Como organizador de eventos, quero poder filtrar o mapa por uma faixa de datas específica e ocultar ocorrências de infraestrutura/segurança pendentes, para identificar locais seguros e adequados para o acontecimento do meu evento.

*  **Critérios de Aceitação:**
  - O usuário pode definir uma faixa de datas personalizada como filtro (RF-FIL-07).
  - O usuário pode selecionar quais tipos de ocorrência deseja exibir ou ocultar.
  - Os filtros de data e tipo funcionam simultaneamente quando aplicados juntos.
  - O mapa reflete os filtros sem necessidade de recarregar a página.

**Filtrar por distância da localização:** Como usuário, quero ativar um filtro de distância (ex: ocorrências em um raio de 500 metros) a partir da minha localização atual, para descobrir rapidamente se há alguma ocorrência de segurança imediata no meu caminho.

*  **Critérios de Aceitação:**
  - O usuário pode ativar um filtro de raio a partir da sua localização atual.
  - A interface permite definir o raio desejado (ex: 100m, 500m, 1km).
  - Apenas ocorrências dentro do raio definido são exibidas no mapa.
  - Caso a permissão de geolocalização seja negada, o sistema exibe mensagem orientando o usuário.

**Filtrar por nível de urgência:** Como usuário, quero filtrar problemas estruturais e de segurança pelo nível de urgência, para poder verificar a situação ao passar pelo local ou evitar passar pelo local.

*  **Critérios de Aceitação:**
  - O filtro de urgência/prioridade está disponível na interface do mapa (RF-FIL-06).
  - O usuário pode selecionar um ou mais níveis de urgência (baixa, média, alta, crítica).
  - Ao aplicar o filtro, apenas ocorrências com o nível de urgência selecionado são exibidas.

**Limpar todos os filtros:** Como usuário, quero um botão visível para limpar todos os filtros aplicados de uma só vez, para restaurar a visão global do mapa sem precisar desmarcar opção por opção.

*  **Critérios de Aceitação:**
  - Um botão claramente visível na interface permite limpar todos os filtros com um único clique (RF-FIL-09).
  - Após limpar, todos os registros voltam a ser exibidos no mapa.
  - O estado de todos os campos de filtro é resetado completamente ao usar o botão.