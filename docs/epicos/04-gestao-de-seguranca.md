# Épico 4: Gestão de Problemas de Segurança

**Descrição**
Este épico permite que usuários reportem problemas de segurança no campus com localização geográfica, imagens, descrição, tipo e prioridade. O sistema deve oferecer transparência por meio de notificações e comentários e fornecer ferramentas para moderação, validação e estatística. O objetivo é agilizar a detecção, o acompanhamento e a solução de incidentes de segurança no campus.

**Requisitos Funcionais Associados**
* RF-SEC-01, RF-SEC-02, RF-SEC-03, RF-SEC-04, RF-SEC-05, RF-SEC-06, RF-SEC-07, RF-SEC-08, RF-SEC-09, RF-SEC-10, RF-SEC-11, RF-SEC-12

---

## Histórias de Usuário (User Stories)

**Reportar problemas com anexo de imagens:** Como membro da comunidade UnB, quero reportar um problema de segurança no mapa, anexando fotos e descrevendo o ocorrido.

*  **Critérios de Aceitação:**
  - O formulário de reporte exige localização, título e tipo do problema.
  - O usuário pode anexar uma ou mais imagens ao reporte (RF-SEC-02).
  - Ao submeter, o problema aparece no mapa com marcador na localização indicada.
  - O sistema exibe mensagem de confirmação após o registro bem-sucedido.

**Reporte anônimo:** Como usuário que presenciou algum problema sensível (como assédio), quero reportar de forma anônima.

*  **Critérios de Aceitação:**
  - O formulário oferece opção de reporte anônimo antes da submissão (RF-SEC-10).
  - Em reportes anônimos, o nome do autor não é exibido para outros usuários.
  - O sistema registra internamente o autor (quando logado) para fins de moderação, sem expor publicamente.
  - A opção de anonimato é claramente identificada no formulário.

**Classificação por tipo e prioridade:** Como usuário, quero classificar o problema por tipo e prioridade para que seja avaliado a gravidade do ocorrido.

*  **Critérios de Aceitação:**
  - O formulário oferece seleção de tipo (iluminação, segurança física, vandalismo, infraestrutura, outro) (RF-SEC-04).
  - O formulário oferece seleção de prioridade (baixa, média, alta, crítica) (RF-SEC-05).
  - Tipo e prioridade são campos obrigatórios para submeter o reporte.
  - A classificação é exibida no card de detalhes do marcador no mapa.

**Acompanhar status:** Como usuário que reportou um problema, quero acompanhar o status da minha ocorrência.

*  **Critérios de Aceitação:**
  - A página de detalhes da ocorrência exibe o status atual de forma destacada (RF-SEC-03).
  - O histórico de mudanças de status é visível, incluindo data e responsável pela alteração (RF-SEC-09).
  - Os status possíveis são: pendente, em andamento, resolvido e arquivado.

**Notificação de mudança de status:** Como usuário que reportou um problema, quero receber notificação quando o status do meu problema mudar.

*  **Critérios de Aceitação:**
  - Ao atualizar o status de uma ocorrência, o autor recebe uma notificação (RF-SEC-07).
  - A notificação indica o status anterior e o novo status atribuído.
  - A notificação é enviada em até 5 minutos após a atualização.

**Validação de problemas:** Como usuário, quero confirmar que um problema reportado por outra pessoa realmente existe, ou discordar de um problema que considero falso.

*  **Critérios de Aceitação:**
  - O usuário pode validar uma ocorrência com um único clique (upvote) (RF-SEC-11).
  - Um mesmo usuário só pode validar a mesma ocorrência uma vez.
  - O usuário pode desfazer sua validação a qualquer momento (RF-ENG-06).
  - A contagem total de validações é exibida no card de detalhes da ocorrência (RF-ENG-05).

**Comentários em ocorrências de outros usuários:** Como usuário, quero comentar em problemas reportados por outros.

*  **Critérios de Aceitação:**
  - Campo de comentário está disponível na página de detalhes de cada ocorrência (RF-SEC-08).
  - Comentários são exibidos em ordem cronológica.
  - O usuário pode editar ou excluir apenas seus próprios comentários.
  - Comentários são visíveis para todos os usuários, incluindo visitantes não logados.

**Filtrar problemas:** Como usuário, quero filtrar problemas no mapa por status, tipo ou localização para encontrar de forma rápida o que me interessa.

*  **Critérios de Aceitação:**
  - Filtros de status, tipo e localização estão disponíveis na interface do mapa (RF-SEC-06).
  - Ao aplicar os filtros, apenas ocorrências correspondentes são exibidas.
  - Os filtros podem ser combinados entre si.
  - Um botão visível permite limpar todos os filtros e restaurar a visão completa do mapa.