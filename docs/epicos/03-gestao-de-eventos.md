# Épico 3: Gestão de Eventos

**Descrição:**
Este épico permite que usuários identificados criem, visualizem, editem, excluam e organizem eventos diretamente sobre um mapa interativo. O objetivo é fornecer uma ferramenta confiável para a divulgação de eventos, tanto acadêmicos quanto culturais e esportivos, garantindo que as informações sejam objetivas e verificáveis visando uma simples centralização de informações acerca de eventos no campus.

**Requisitos Funcionais Associados:** 
* RF-EVT-01, RF-EVT-02, RF-EVT-03, RF-EVT-04, RF-EVT-05, RF-EVT-06, RF-EVT-07, RF-EVT-08, RF-EVT-09, RF-EVT-10, RF-EVT-11, RF-EVT-12, RF-EVT-13

---

## Histórias de Usuário (User Stories)

**Impedir agendamento retroativo:** Como usuário, quero que o sistema me impeça de criar um evento com data passada.

*  **Critérios de Aceitação:**
  - O campo de data não permite selecionar datas anteriores à data atual.
  - Caso o usuário tente submeter o formulário com data passada, uma mensagem de erro é exibida.
  - A mensagem indica claramente que a data do evento deve ser futura.

**Notificar alterações a interessados:** Como usuário que manifestou interesse em um evento, quero receber notificações se o evento for alterado ou cancelado.

*  **Critérios de Aceitação:**
  - Ao salvar qualquer alteração em um evento (data, local, status), todos os usuários que manifestaram interesse recebem uma notificação.
  - A notificação indica o que mudou (ex: "A data do evento X foi alterada para ...").
  - Em caso de cancelamento, a notificação informa explicitamente que o evento foi cancelado.
  - A notificação é gerada em até 5 minutos após a alteração ser salva.

**Criação automática de eventos recorrentes:** Como organizador de um evento recorrente (ex: quinzenal), quero criar vários eventos com um único cadastro de evento, definindo a frequência, para não precisar criar cada ocorrência manualmente.

*  **Critérios de Aceitação:**
  - O formulário de criação de evento oferece opção de recorrência (semanal, quinzenal, mensal).
  - O usuário define a data de início e o período de recorrência.
  - O sistema cria automaticamente todas as ocorrências dentro do período definido.
  - Cada ocorrência aparece individualmente no mapa com sua data correta.
  - O usuário pode editar ou excluir uma ocorrência específica sem afetar as demais.

**Feedback ao organizador:** Como organizador, quero receber uma mensagem de confirmação após criar, editar ou excluir um evento, para ter certeza que a ação foi concluída com sucesso.

*  **Critérios de Aceitação:**
  - Após criar, editar ou excluir um evento, uma mensagem de sucesso é exibida na interface.
  - A mensagem indica claramente qual ação foi realizada (ex: "Evento criado com sucesso").
  - Em caso de falha, uma mensagem de erro é exibida orientando o usuário.

**Ativar lembrete:** Como usuário, quero ativar um lembrete para um evento.

*  **Critérios de Aceitação:**
  - O usuário pode ativar um lembrete em qualquer evento que manifestou interesse.
  - O sistema envia uma notificação ao usuário antes do início do evento (ex: 1 hora antes).
  - O usuário pode desativar o lembrete a qualquer momento antes do evento ocorrer.