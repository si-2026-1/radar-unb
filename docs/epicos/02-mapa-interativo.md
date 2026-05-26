# Épico 2: Mapa Interativo

**Descrição:**
Este épico trata do "coração" visual da aplicação: a renderização do mapa, o consumo eficiente de coordenadas e a visualização de dados espaciais. O foco é garantir que os usuários ganhem consciência situacional do campus através de uma interface fluida, garantindo alta performance no carregamento de múltiplos marcadores e excelente responsividade em diferentes tamanhos de tela.

**Requisitos Funcionais Associados:**

* RF-MAP-01, RF-MAP-02, RF-MAP-03, RF-MAP-04, RF-MAP-05, RF-MAP-06, RF-MAP-07

---

## Histórias de Usuário (User Stories)

* **US2.1:** Como usuário, quero visualizar um mapa interativo e responsivo do campus da UnB, para ter uma visão geral das ocorrências cadastradas.

  **Critérios de Aceitação:**
  - O mapa exibe a região do campus da UnB como área padrão ao carregar, sem necessidade de busca ou navegação manual.
  - Os marcadores do mapa são exibidos em até 5 segundos em conexão 4G.
  - A interface é utilizável em smartphones (mínimo 360px de largura) e em desktops.
  - O mapa pode ser acessado sem login (modo leitura público).

* **US2.2:** Como usuário, quero clicar em um marcador georreferenciado no mapa, para visualizar em um card ou modal os detalhes do evento ou problema (título, descrição, foto).

  **Critérios de Aceitação:**
  - Ao clicar em um marcador, um card ou modal é exibido com título, descrição e foto (quando disponível).
  - O card/modal pode ser fechado com um clique fora dele ou em um botão explícito de fechar.
  - A ação de toque (mobile) abre o card corretamente, sem necessidade de duplo toque.
  - Se um campo opcional (ex: foto) estiver ausente, o card ainda é exibido sem erros.

* **US2.3:** Como usuário, quero aplicar filtros (por tipo, data e localização) no mapa, para focar apenas em eventos acadêmicos ou apenas em problemas de segurança recentes.

  **Critérios de Aceitação:**
  - Os filtros de tipo, data e localização estão disponíveis e acessíveis na interface do mapa.
  - Ao aplicar um filtro, o mapa atualiza os marcadores sem recarregar a página completa.
  - Filtros podem ser aplicados simultaneamente (ex: tipo + data).
  - Um botão visível permite limpar todos os filtros e restaurar a visualização completa do mapa.

* **US2.4:** Como usuário, quero visualizar as ocorrências e eventos como marcadores distintos no mapa, para diferenciar rapidamente o tipo de cada registro sem precisar clicar no ícone.

  **Critérios de Aceitação:**
  - Marcadores de eventos e de ocorrências de segurança possuem cores ou ícones visualmente distintos.
  - Uma legenda explicando o significado de cada tipo de marcador está visível ou acessível na interface do mapa.
  - A diferenciação é perceptível sem necessidade de clicar no marcador.

* **US2.5:** Como usuário, quero que marcadores muito próximos sejam agrupados quando o zoom estiver distante, para evitar a poluição visual e manter o mapa legível.

  **Critérios de Aceitação:**
  - Marcadores próximos são agrupados automaticamente (cluster) quando o zoom está afastado.
  - O cluster exibe a contagem de marcadores agrupados.
  - Ao aumentar o zoom sobre um cluster, os marcadores individuais são exibidos.
  - O desempenho do mapa não é degradado com o agrupamento de muitos marcadores.

* **US2.6:** Como usuário, quero ver a minha posição atual no mapa, para me orientar em relação aos problemas e eventos ao meu redor.

  **Critérios de Aceitação:**
  - Existe um botão ou ação clara para solicitar a exibição da localização atual do usuário.
  - O sistema solicita permissão de geolocalização ao dispositivo antes de exibir a posição.
  - Um marcador visual diferenciado indica a posição atual do usuário no mapa.
  - Caso a permissão de geolocalização seja negada, o sistema exibe uma mensagem explicativa sem travar a interface.

* **US2.7:** Como usuário, quero que o mapa carregue os dados dinamicamente conforme mudo de região, para garantir o desempenho e poupar consumo de dados.

  **Critérios de Aceitação:**
  - Ao arrastar ou aplicar zoom no mapa, novos dados da região visível são carregados sem recarregar a página completa.
  - Um indicador visual de carregamento é exibido enquanto os dados estão sendo buscados.
  - Marcadores já carregados não são duplicados ao mover o mapa.
  - O carregamento dinâmico não interrompe a navegação do usuário no mapa.

* **US2.8:** Como usuário, quero que o mapa não me permita navegar para fora do campus da UnB, para manter o foco na área de cobertura da plataforma. *(RF-MAP-06)*

  **Critérios de Aceitação:**
  - A navegação pelo mapa é limitada à área geográfica do campus da UnB.
  - Ao tentar arrastar o mapa para além dos limites definidos, o mapa retorna automaticamente à área de cobertura.
  - O nível mínimo de zoom mantém o campus da UnB sempre visível na tela.