# Radar UnB

Plataforma colaborativa de geolocalização para mapeamento, divulgação e acompanhamento de problemas estruturais, segurança e eventos no campus da UnB.

## O Problema

A comunidade da UnB enfrenta dificuldade para acessar, divulgar e acompanhar informações geolocalizadas sobre problemas estruturais, ocorrências de segurança e eventos acadêmicos no campus, pois esses dados estão dispersos em múltiplos canais.

## A Solução

Uma plataforma digital interativa (web e mobile) que centraliza essas informações em um único ambiente georreferenciado. O objetivo é melhorar a percepção de segurança, facilitar a descoberta de eventos e estimular a participação ativa da comunidade através de um mapa inteligente e colaborativo.

---

## Integrantes

| Nome | Matrícula |
| --- | --- |
| Caetano Korilo | 212006737 |
| Pablo Trajano | 202017020 |
| Rodrigo Torreão| 211066196 |
| Gabriela Costa | 180120859 | 


---

## Configuração do Ambiente

### Pré-requisitos

- **Python 3.8+** - Para execução do MkDocs
- **pip** - Gerenciador de pacotes Python
- **git** - Controle de versão

### Instalação

```bash
# Crie um ambiente virtual
python3 -m venv .venv

# Ative o ambiente virtual
source .venv/bin/activate  # Linux/Mac
# ou
.venv\Scripts\activate     # Windows

# Instale as dependências
pip install mkdocs mkdocs-material
```

---

## Estrutura do Projeto

```text
.
├── docs/                    # Documentação do projeto
│   ├── index.md            # Página inicial
│   ├── requisitos/         # Requisitos funcionais e não-funcionais
│   ├── epicos/             # Épicos do projeto
│   └── ...
├── overrides/              # Customizações do tema
│   └── partials/           # Componentes HTML personalizados
├── mkdocs.yml              # Configuração do MkDocs
└── README.md               # Este arquivo
```

- **docs/**: Todos os arquivos markdown da documentação
- **mkdocs.yml**: Configuração do site (tema, navegação, plugins)
- **overrides/**: Customizações visuais do tema Material

---

## Desenvolvimento

### Executar Localmente

```bash
# Ative o ambiente virtual (se ainda não ativado)
source .venv/bin/activate

# Inicie o servidor de desenvolvimento
mkdocs serve
```

O site estará disponível em `http://127.0.0.1:8000`

**Recursos do servidor de desenvolvimento:**
- Auto-reload: Alterações nos arquivos são refletidas automaticamente
- Live preview: Visualize mudanças em tempo real
- Ctrl+C para interromper

### Build para Produção

```bash
# Gera os arquivos estáticos na pasta site/
mkdocs build
```

---

## Comandos Úteis

```bash
# Servidor de desenvolvimento (com endereço específico)
mkdocs serve -a 0.0.0.0:8000

# Build limpo (remove cache anterior)
mkdocs build --clean

# Verificar configuração
mkdocs --verbose build

# Listar comandos disponíveis
mkdocs --help
```
