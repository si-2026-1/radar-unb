# Modelagem Conceitual do Banco de Dados

## Visão Geral

O modelo conceitual identifica as entidades fundamentais do **Radar UnB**, seus atributos e os relacionamentos entre elas, derivados diretamente dos requisitos funcionais levantados. O objetivo nesta etapa é representar o domínio do problema de forma independente de tecnologia.

---

## Entidades

### USUARIO
Representa um membro da comunidade UnB cadastrado na plataforma. Corresponde aos requisitos RF-ACE-01 a RF-ACE-06.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| matricula | Texto | PK | Matrícula universitária (ex: 211066196) |
| nome | Texto | Obrigatório | Nome completo |
| email | Texto | Único, Obrigatório | E-mail de cadastro |
| senha_hash | Texto | Obrigatório | Senha criptografada |
| tipo | Enumerado | Obrigatório | `membro` ou `admin` |
| status | Enumerado | Obrigatório | `ativo`, `inativo` ou `pendente` |
| email_verificado | Booleano | Obrigatório | Confirmação de e-mail (RF-ACE-06) |
| created_at | Data/Hora | Obrigatório | Data de cadastro |
| updated_at | Data/Hora | Obrigatório | Última atualização |

---

### OCORRENCIA
Representa um problema de segurança ou infraestrutura registrado no campus com geolocalização. Corresponde aos requisitos RF-SEC-01 a RF-SEC-12.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| titulo | Texto | Obrigatório | Título curto da ocorrência |
| descricao | Texto longo | Opcional | Descrição detalhada (RF-SEC-02) |
| tipo | Enumerado | Obrigatório | Categoria: `iluminacao`, `seguranca_fisica`, `vandalismo`, `infraestrutura`, `outro` (RF-SEC-04) |
| status | Enumerado | Obrigatório | `pendente`, `em_andamento`, `resolvido`, `arquivado` (RF-SEC-03) |
| prioridade | Enumerado | Obrigatório | `baixa`, `media`, `alta`, `critica` (RF-SEC-05) |
| latitude | Decimal | Obrigatório | Coordenada geográfica (RF-SEC-01) |
| longitude | Decimal | Obrigatório | Coordenada geográfica (RF-SEC-01) |
| anonimo | Booleano | Obrigatório | Indica reporte anônimo (RF-SEC-10) |
| usuario_id | Identificador | FK, Opcional | Autor (nulo se anônimo) |
| created_at | Data/Hora | Obrigatório | Data de registro |
| updated_at | Data/Hora | Obrigatório | Última atualização |

---

### EVENTO
Representa um evento acadêmico, cultural ou esportivo publicado no mapa. Corresponde aos requisitos RF-EVT-01 a RF-EVT-09.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| titulo | Texto | Obrigatório | Nome do evento (RF-EVT-02) |
| descricao | Texto longo | Opcional | Detalhes do evento (RF-EVT-07) |
| categoria | Enumerado | Obrigatório | `academico`, `cultural`, `esportivo`, `social`, `outro` (RF-EVT-05) |
| data_inicio | Data/Hora | Obrigatório | Início do evento (RF-EVT-02, RF-EVT-08) |
| data_fim | Data/Hora | Opcional | Encerramento do evento (RF-EVT-08) |
| latitude | Decimal | Obrigatório | Coordenada geográfica (RF-EVT-02) |
| longitude | Decimal | Obrigatório | Coordenada geográfica (RF-EVT-02) |
| link_externo | Texto | Opcional | URL com mais informações (RF-EVT-09) |
| status | Enumerado | Obrigatório | `ativo`, `cancelado`, `encerrado` |
| usuario_id | Identificador | FK, Obrigatório | Autor do evento |
| created_at | Data/Hora | Obrigatório | Data de cadastro |
| updated_at | Data/Hora | Obrigatório | Última atualização |

---

### MIDIA
Representa arquivos de imagem anexados a ocorrências ou eventos. Corresponde aos requisitos RF-SEC-02 e RF-EVT-06.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| url | Texto | Obrigatório | Caminho/URL do arquivo armazenado |
| tipo | Enumerado | Obrigatório | `imagem` (extensível para `video`) |
| entidade_tipo | Enumerado | Obrigatório | `ocorrencia` ou `evento` |
| entidade_id | Identificador | Obrigatório | ID do registro ao qual pertence |
| usuario_id | Identificador | FK, Opcional | Usuário que enviou o arquivo |
| created_at | Data/Hora | Obrigatório | Data do envio |

---

### COMENTARIO
Representa uma interação textual de um usuário em uma ocorrência. Corresponde aos requisitos RF-SEC-08 e RF-ENG-03.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| conteudo | Texto longo | Obrigatório | Texto do comentário |
| usuario_id | Identificador | FK, Obrigatório | Autor do comentário |
| ocorrencia_id | Identificador | FK, Obrigatório | Ocorrência comentada |
| created_at | Data/Hora | Obrigatório | Data de publicação |
| updated_at | Data/Hora | Obrigatório | Última edição |

---

### VALIDACAO
Representa o upvote/confirmação de um usuário em uma ocorrência, atestando sua veracidade. Corresponde aos requisitos RF-SEC-11, RF-ENG-01, RF-ENG-05 e RF-ENG-06.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| usuario_id | Identificador | FK, Obrigatório | Usuário que validou |
| ocorrencia_id | Identificador | FK, Obrigatório | Ocorrência validada |
| created_at | Data/Hora | Obrigatório | Data da validação |

> **Restrição de integridade:** um mesmo usuário só pode validar uma dada ocorrência uma vez (RF-ENG-01, RF-ENG-06).

---

### HISTORICO_STATUS
Registra cada mudança de status de uma ocorrência, garantindo auditoria completa. Corresponde ao requisito RF-SEC-09.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| ocorrencia_id | Identificador | FK, Obrigatório | Ocorrência relacionada |
| status_anterior | Enumerado | Opcional | Status antes da mudança |
| status_novo | Enumerado | Obrigatório | Novo status atribuído |
| responsavel_id | Identificador | FK, Opcional | Usuário/admin que realizou a mudança |
| observacao | Texto longo | Opcional | Justificativa ou nota da alteração |
| created_at | Data/Hora | Obrigatório | Momento da mudança |

---

### TAG
Representa palavras-chave para categorização e busca de ocorrências e eventos. Corresponde ao requisito RF-FIL-03.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| nome | Texto | Único, Obrigatório | Texto da tag (ex: "buraco", "palestra") |
| created_at | Data/Hora | Obrigatório | Data de criação |

---

### DENUNCIA
Representa uma denúncia de conteúdo inadequado ou falso feita por um usuário. Corresponde ao requisito RF-ENG-07.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| motivo | Texto longo | Obrigatório | Descrição do motivo da denúncia |
| usuario_id | Identificador | FK, Obrigatório | Usuário que denunciou |
| entidade_tipo | Enumerado | Obrigatório | `ocorrencia`, `evento` ou `comentario` |
| entidade_id | Identificador | Obrigatório | ID do conteúdo denunciado |
| status | Enumerado | Obrigatório | `pendente`, `analisada`, `arquivada` |
| created_at | Data/Hora | Obrigatório | Data da denúncia |

---

### NOTIFICACAO
Representa um aviso gerado pelo sistema para um usuário sobre atualizações relevantes. Corresponde aos requisitos RF-SEC-07 e RF-ENG-04.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| usuario_id | Identificador | FK, Obrigatório | Destinatário |
| mensagem | Texto longo | Obrigatório | Conteúdo da notificação |
| lida | Booleano | Obrigatório | Indica se foi lida |
| entidade_tipo | Enumerado | Opcional | `ocorrencia`, `evento` ou `comentario` |
| entidade_id | Identificador | Opcional | ID do registro de origem |
| created_at | Data/Hora | Obrigatório | Data de criação |

---

### HISTORICO_BUSCA
Registra as buscas realizadas por um usuário autenticado. Corresponde ao requisito RF-FIL-08.

| Atributo | Tipo Conceitual | Restrição | Descrição |
|---|---|---|---|
| id | Identificador | PK | Chave primária |
| usuario_id | Identificador | FK, Obrigatório | Usuário que realizou a busca |
| query | Texto | Obrigatório | Termo pesquisado |
| filtros | Estrutura | Opcional | Filtros aplicados na busca (tipo, data, localização) |
| created_at | Data/Hora | Obrigatório | Data da busca |

---

## Relacionamentos

| Relacionamento | Cardinalidade | Descrição |
|---|---|---|
| USUARIO — cria → OCORRENCIA | 1:N (opcional) | Um usuário pode criar várias ocorrências; ocorrências anônimas não têm usuário |
| USUARIO — cria → EVENTO | 1:N | Um usuário pode criar vários eventos |
| USUARIO — faz → COMENTARIO | 1:N | Um usuário pode comentar em várias ocorrências |
| USUARIO — faz → VALIDACAO | 1:N | Um usuário pode validar várias ocorrências, mas cada ocorrência apenas uma vez |
| USUARIO — faz → DENUNCIA | 1:N | Um usuário pode denunciar vários conteúdos |
| USUARIO — recebe → NOTIFICACAO | 1:N | Um usuário pode ter várias notificações |
| USUARIO — tem → HISTORICO_BUSCA | 1:N | Um usuário pode ter várias buscas salvas |
| OCORRENCIA — possui → MIDIA | 1:N | Uma ocorrência pode ter várias imagens |
| OCORRENCIA — possui → COMENTARIO | 1:N | Uma ocorrência pode ter vários comentários |
| OCORRENCIA — recebe → VALIDACAO | 1:N | Uma ocorrência pode ser validada por vários usuários |
| OCORRENCIA — possui → HISTORICO_STATUS | 1:N | Uma ocorrência tem todo seu histórico de status registrado |
| OCORRENCIA — possui → TAG | N:M | Ocorrências e tags têm relação muitos-para-muitos |
| EVENTO — possui → MIDIA | 1:N | Um evento pode ter várias imagens |
| EVENTO — possui → TAG | N:M | Eventos e tags têm relação muitos-para-muitos |
| HISTORICO_STATUS — atualizado por → USUARIO | N:1 | Várias atualizações de status podem ser feitas pelo mesmo responsável |
