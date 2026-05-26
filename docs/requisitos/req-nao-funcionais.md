# Requisitos Não Funcionais

**Descrição:**
Os requisitos não funcionais especificam os critérios de qualidade, desempenho, segurança, usabilidade e as restrições técnicas sob as quais o sistema **Radar UnB** deve operar, garantindo uma boa experiência para a comunidade.

---

## Lista de Requisitos Não Funcionais (RNF)

### Desempenho

* **RNF-DES-01** – O sistema deve responder às ações do usuário em até 3 segundos em condições normais de uso.
* **RNF-DES-02** – O mapa interativo deve carregar e renderizar os marcadores iniciais em até 5 segundos em conexão 4G.
* **RNF-DES-03** – Buscas textuais e aplicação de filtros devem retornar resultados em até 2 segundos.

---

### Disponibilidade

* **RNF-DIS-01** – O sistema deve estar disponível 24 horas por dia, 7 dias por semana, com taxa de disponibilidade mínima de 99% ao mês.
* **RNF-DIS-02** – Janelas de manutenção programada devem ser realizadas em horários de baixo acesso e comunicadas aos usuários com pelo menos 24 horas de antecedência.

---

### Segurança

* **RNF-SEG-01** – As senhas dos usuários devem ser armazenadas utilizando algoritmo de hash seguro (ex: bcrypt), nunca em texto puro. *(Relacionado a: RF-ACE-01, tabela `usuario.senha_hash`)*
* **RNF-SEG-02** – Todo o tráfego de dados entre cliente e servidor deve ser protegido por TLS/HTTPS.
* **RNF-SEG-03** – O sistema deve garantir a proteção e a privacidade dos dados pessoais dos usuários em conformidade com a LGPD (Lei nº 13.709/2018).
* **RNF-SEG-04** – Sessões inativas devem ser encerradas automaticamente após o período configurado, impedindo acesso não autorizado. *(Relacionado a: RF-ACE-07)*

---

### Usabilidade e Acessibilidade

* **RNF-USA-01** – A interface deve ser intuitiva e acessível para todos os perfis de usuário da comunidade acadêmica, sem necessidade de treinamento prévio.
* **RNF-USA-02** – O sistema deve ser responsivo e funcionar corretamente em dispositivos móveis e desktops, adaptando-se a telas de diferentes tamanhos.
* **RNF-USA-03** – Mensagens de erro devem ser claras, escritas em linguagem acessível, e orientar o usuário sobre como corrigir o problema.

---

### Escalabilidade e Capacidade

* **RNF-ESC-01** – O sistema deve suportar no mínimo 500 usuários simultâneos sem degradação perceptível de desempenho. *(Relacionado a: RF-MAP-01)*
* **RNF-ESC-02** – A estrutura do banco de dados deve suportar crescimento contínuo de registros (ocorrências, eventos, usuários) sem necessidade de reestruturação do esquema.

---

### Confiabilidade

* **RNF-CON-01** – Os dados da plataforma devem ser armazenados com mecanismo de backup regular, garantindo recuperação em caso de falha.
* **RNF-CON-02** – Em caso de falha ou erro inesperado, o sistema deve exibir mensagens amigáveis ao usuário sem expor detalhes técnicos internos (stack traces, mensagens de banco de dados, etc.).


