# Requisitos Funcionais

**Descrição:**  
Os requisitos funcionais definem as ações, os comportamentos e as funcionalidades específicas que a plataforma **Radar UnB** deve possuir para que os usuários consigam realizar suas tarefas e alcançar seus objetivos dentro do sistema.

---

## Lista de Requisitos Funcionais (RF)

### Gestão de Identificação e Acesso

* **RF-ACE-01** – O sistema deve permitir o cadastro de usuários.
* **RF-ACE-02** – O sistema deve permitir login e autenticação de usuários.
* **RF-ACE-03** – O sistema deve permitir recuperação de senha via email.
* **RF-ACE-04** – O sistema deve permitir logout seguro encerrando a sessão ativa.
* **RF-ACE-05** – O sistema deve permitir que usuários editem seu próprio perfil (nome, email).
* **RF-ACE-06** – O sistema deve exigir confirmação de email durante cadastro.
* **RF-ACE-07** - O sistema deve encerrar a sessão automaticamente após período de inatividade configurável (ex: padrão - 30 minutos).
* **RF-ACE-08** - O sistema deve permitir que o usuário solicite a exclusão de sua conta.
* **RF-ACE-09** - O sistema deve notificar o usuário por e-mail sempre que ocorrer um evento sensível (login de novo dispositivo, alteração de senha, solicitação de exclusão de conta).

### Mapa Interativo e Visualização

* **RF-MAP-01** – O sistema deve exibir um mapa interativo do campus da UnB.
* **RF-MAP-02** – O sistema deve exibir detalhes ao clicar em um ponto no mapa.
* **RF-MAP-03** – O sistema deve agrupar (clusterizar) marcadores próximos.
* **RF-MAP-04** – O sistema deve diferenciar marcadores por categoria visualmente.
* **RF-MAP-05** – O sistema deve exibir a geolocalização em tempo real do usuário.
* **RF-MAP-06** – O sistema deve restringir a navegação para impedir que o usuário arraste infinitamente a tela para fora da área de cobertura.
* **RF-MAP-07** – O sistema deve realizar a atualização dos dados de forma assíncrona, garantindo a continuidade da navegação do usuário.

### Gestão de Segurança (Pilar Segurança)

* **RF-SEC-01** – O sistema deve permitir ao usuário registrar problemas com localização geográfica.
* **RF-SEC-02** – O sistema deve permitir anexar imagens e descrições às ocorrências.
* **RF-SEC-03** – O sistema deve permitir acompanhar o status de um problema (ex: pendente, resolvido).
* **RF-SEC-04** – O sistema deve permitir classificar problemas por tipo (iluminação, segurança física, vandalismo, etc.).
* **RF-SEC-05** – O sistema deve permitir definir nível de prioridade/urgência para cada ocorrência.
* **RF-SEC-06** – O sistema deve permitir filtrar problemas por status, tipo e localização.
* **RF-SEC-07** – O sistema deve notificar usuários sobre atualizações de status em ocorrências que reportaram.
* **RF-SEC-08** – O sistema deve permitir comentários ou interações nas ocorrências de segurança.
* **RF-SEC-09** – O sistema deve manter histórico de alterações de status e responsáveis.
* **RF-SEC-10** – O sistema deve permitir reportar problemas de forma anônima.
* **RF-SEC-11** – O sistema deve permitir que usuários validem a veracidade de problemas reportados.
* **RF-SEC-12** – O sistema deve exibir estatísticas e relatórios de segurança do campus.

### Gestão de Eventos (Pilar Eventos)

* **RF-EVT-01** – O sistema deve permitir ao usuário cadastrar eventos no mapa.
* **RF-EVT-02** – O sistema deve exigir campos obrigatórios para cadastro de eventos (título, data, horário, local).
* **RF-EVT-03** – O sistema deve permitir que usuários editem eventos cadastrados por eles mesmos.
* **RF-EVT-04** – O sistema deve permitir que usuários excluam eventos cadastrados por eles mesmos.
* **RF-EVT-05** – O sistema deve permitir categorizar eventos por tipo (acadêmico, cultural, esportivo, etc.).
* **RF-EVT-06** – O sistema deve permitir anexar imagens aos eventos.
* **RF-EVT-07** – O sistema deve permitir adicionar descrição detalhada ao evento.
* **RF-EVT-08** – O sistema deve permitir definir horário de início e fim do evento.
* **RF-EVT-09** – O sistema deve permitir adicionar link externo para mais informações sobre o evento.
* **RF-EVT-10** -  O sistema deve permitir que qualquer visitante visualize os eventos no mapa (modo leitura público).
* **RF-EVT-11** - O sistema deve exigir um status do evento (agendado, cancelado, encerrado).
* **RF-EVT-12** - O sistema deve permitir usuários manifestarem interesse em eventos.
* **RF-EVT-13** - O sistema deve notificar usuários interessados em algum evento sobre alterações (nova data ou local).

### Filtragem e Busca

* **RF-FIL-01** – O sistema deve permitir filtrar ocorrências por tipo (problema ou evento).
* **RF-FIL-02** – O sistema deve permitir filtrar ocorrências por localização e data.
* **RF-FIL-03** – O sistema deve permitir busca por palavras-chave/tags associadas às ocorrências.
* **RF-FIL-04** – O sistema deve oferecer sugestões de busca automática enquanto o usuário digita.
* **RF-FIL-05** – O sistema deve permitir filtrar ocorrências por status (pendente, em andamento, resolvido).
* **RF-FIL-06** – O sistema deve permitir filtrar ocorrências por nível de prioridade/urgência.
* **RF-FIL-07** – O sistema deve permitir filtrar por faixa de datas (período personalizado).
* **RF-FIL-08** – O sistema deve manter histórico de buscas realizadas pelo usuário.
* **RF-FIL-09** – O sistema deve permitir limpar todos os filtros com um único clique.

### Engajamento e Gestão de Registros (Pilar Engajamento Comunitário)

* **RF-ENG-01** – O sistema deve permitir que usuários validem ou confirmem ocorrências.
* **RF-ENG-02** – O sistema deve permitir editar ou excluir registros feitos pelo próprio usuário.
* **RF-ENG-03** – O sistema deve permitir comentários e discussões nas ocorrências registradas.
* **RF-ENG-04** – O sistema deve notificar usuários sobre atualizações em ocorrências que interagiram ou validaram.
* **RF-ENG-05** – O sistema deve exibir contagem de validações/upvotes para cada ocorrência.
* **RF-ENG-06** – O sistema deve permitir que usuários desfaçam suas validações.
* **RF-ENG-07** – O sistema deve permitir denúncia de conteúdo inadequado ou falso.
* **RF-ENG-08** – O sistema deve permitir que usuários editem apenas campos específicos de seus registros (preservando histórico).

