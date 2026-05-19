---
changelog:
  - author: Caetano Korilo
    date: 2026-05-12
    changes: Criação do documento
  - author: Caetano Korilo
    date: 2026-05-19
    changes: Reorganização dos requisitos em grupos alinhados aos pilares do escopo e adição de novos requisitos funcionais (RF13-RF28)
---

# Requisitos Funcionais

**Descrição:**  
Os requisitos funcionais definem as ações, os comportamentos e as funcionalidades específicas que a plataforma **Radar UnB** deve possuir para que os usuários consigam realizar suas tarefas e alcançar seus objetivos dentro do sistema.

---

## Lista de Requisitos Funcionais (RF)

### Gestão de Identificação e Acesso

* **RF01** – O sistema deve permitir o cadastro de usuários.
* **RF02** – O sistema deve permitir login e autenticação de usuários.
* **RF03** – O sistema deve permitir recuperação de senha via email.
* **RF04** – O sistema deve permitir logout seguro encerrando a sessão ativa.
* **RF05** – O sistema deve permitir que usuários editem seu próprio perfil (nome, email).
* **RF06** – O sistema deve exigir confirmação de email durante cadastro.

### Mapa Interativo e Visualização

* **RF07** – O sistema deve exibir um mapa interativo do campus da UnB.
* **RF08** – O sistema deve exibir detalhes ao clicar em um ponto no mapa.

### Gestão de Segurança (Pilar Segurança)

* **RF09** – O sistema deve permitir ao usuário registrar problemas com localização geográfica.
* **RF10** – O sistema deve permitir anexar imagens e descrições às ocorrências.
* **RF11** – O sistema deve permitir acompanhar o status de um problema (ex: pendente, resolvido).

### Gestão de Eventos (Pilar Eventos)

* **RF12** – O sistema deve permitir ao usuário cadastrar eventos no mapa.
* **RF17** – O sistema deve exigir campos obrigatórios para cadastro de eventos (título, data, horário, local).
* **RF18** – O sistema deve permitir que usuários editem eventos cadastrados por eles mesmos.
* **RF19** – O sistema deve permitir que usuários excluam eventos cadastrados por eles mesmos.
* **RF20** – O sistema deve permitir categorizar eventos por tipo (acadêmico, cultural, esportivo, etc.).
* **RF21** – O sistema deve permitir anexar imagens aos eventos.
* **RF22** – O sistema deve permitir adicionar descrição detalhada ao evento.
* **RF23** – O sistema deve permitir definir horário de início e fim do evento.
* **RF24** – O sistema deve permitir adicionar link externo para mais informações sobre o evento.

### Filtragem e Busca

* **RF25** – O sistema deve permitir filtrar ocorrências por tipo (problema ou evento).
* **RF26** – O sistema deve permitir filtrar ocorrências por localização e data.

### Engajamento e Gestão de Registros (Pilar Engajamento Comunitário)

* **RF27** – O sistema deve permitir que usuários validem ou confirmem ocorrências.
* **RF28** – O sistema deve permitir editar ou excluir registros feitos pelo próprio usuário.

