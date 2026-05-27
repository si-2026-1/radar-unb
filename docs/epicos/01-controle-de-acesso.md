# Épico 1: Controle de Acesso e Identidade

**Descrição:**  
Este épico estabelece a base de identidade e segurança da plataforma, garantindo que apenas usuários legítimos, devidamente identificados, possam acessar o sistema. O objetivo é prevenir spam, proteger dados sensíveis, oferecer mecanismos de recuperação de acesso, edição de perfil e encerramento de sessão.

**Requisitos Funcionais Associados:**  
* RF-ACE-01, RF-ACE-02, RF-ACE-03, RF-ACE-04, RF-ACE-05, RF-ACE-06, RF-ACE-07, RF-ACE-08, RF-ACE-09

---

## Histórias de Usuário (User Stories)

**Cadastro de usuário na plataforma:** Como membro da comunidade UnB, quero criar uma conta na plataforma utilizando meu e-mail, para poder registrar e interagir com as ocorrências.

*  **Critérios de Aceitação:**
  - O formulário de cadastro exige nome, e-mail, matrícula e senha.
  - O sistema valida o formato do e-mail antes de prosseguir.
  - Após o cadastro, um e-mail de confirmação é enviado automaticamente (RF-ACE-06).
  - A conta só é ativada após o usuário confirmar o e-mail recebido.
  - Não é possível cadastrar dois usuários com o mesmo e-mail ou matrícula.

**Login na aplicação:** Como usuário cadastrado, quero fazer login com segurança na aplicação, para acessar meu perfil e gerenciar minhas publicações.

*  **Critérios de Aceitação:**
  - O login aceita o e-mail e a senha cadastrados.
  - Credenciais incorretas exibem mensagem de erro sem revelar qual campo está errado.
  - Após login bem-sucedido, o usuário é redirecionado para a tela principal com o mapa.
  - Contas com e-mail não confirmado não conseguem fazer login.

**Recuperação de senha:** Como usuário que esqueceu a senha, quero solicitar um link de recuperação enviado para meu e-mail, para definir uma nova senha.

*  **Critérios de Aceitação:**
  - O usuário pode solicitar a recuperação informando apenas o e-mail cadastrado.
  - Um e-mail com link de recuperação é enviado em até 5 minutos.
  - O link de recuperação expira após 24 horas.
  - Ao acessar o link válido, o usuário pode definir uma nova senha.
  - Link expirado ou inválido exibe mensagem de erro orientando o usuário a solicitar novamente.

**Logout automático por inatividade:** Como usuário que esqueceu/não fez logout, quero que minha sessão seja encerrada automaticamente após 30 minutos de inatividade, para que outras pessoas não acessem minha conta pelos meus dispositivos.

*  **Critérios de Aceitação:**
  - A sessão é encerrada automaticamente após 30 minutos sem atividade do usuário (RF-ACE-07).
  - Ao retornar após o encerramento, o usuário é redirecionado para a tela de login.
  - O sistema não exibe dados do usuário após o encerramento da sessão.

**Exclusão permanente da conta:** Como usuário que quer deixar a plataforma, quero solicitar a exclusão permanente da minha conta.

*  **Critérios de Aceitação:**
  - A opção de exclusão de conta está disponível nas configurações do perfil.
  - O sistema exibe uma mensagem de confirmação antes de processar a solicitação.
  - O usuário recebe um e-mail confirmando o recebimento da solicitação de exclusão (RF-ACE-09).
  - Após a exclusão, os dados pessoais do usuário são removidos ou anonimizados.
