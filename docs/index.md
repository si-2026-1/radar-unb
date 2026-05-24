# Radar UnB: Plataforma de Divulgação Geoespacial

Plataforma colaborativa de geolocalização para mapeamento, divulgação e acompanhamento de problemas estruturais, segurança e eventos no campus da UnB.


## O Problema
A comunidade da UnB enfrenta dificuldade para acessar, divulgar e acompanhar informações geolocalizadas sobre problemas estruturais, ocorrências de segurança e eventos acadêmicos no campus, pois esses dados estão dispersos em múltiplos canais e não contam com uma plataforma centralizada, colaborativa e visual.

>  [Documento de Problema](problema/problema.md)

## A Solução (Proposta de Valor)
Uma plataforma digital interativa (web e mobile) desenvolvida para centralizar essas informações em um único ambiente georreferenciado. O objetivo é melhorar a percepção de segurança, facilitar a descoberta de eventos e estimular a participação ativa de estudantes, professores, servidores e visitantes da universidade através de um mapa inteligente e colaborativo.

## Escopo do Projeto

> [Documento de Escopo](escopo/escopo.md)

**O que o sistema faz:**
* Disponibiliza um mapa interativo do campus para visualização de dados espaciais.
* Permite marcação geográfica, registro de ocorrências (com fotos e descrições) e cadastro de eventos acadêmicos.
* Oferece filtros dinâmicos (por categoria, localização e data) e interação comunitária (validação/upvotes de ocorrências).
* Mantém o acompanhamento de status das situações reportadas (ex: pendente, resolvido).

**O que o sistema NÃO faz:**
* Não substitui sistemas oficiais de segurança ou ouvidoria da UnB.
* Não possui integração direta com os sistemas administrativos da instituição.
* Não monitora o campus em tempo real via sensores físicos de hardware.
* Não garante a resolução automática dos problemas.

## Principais Funcionalidades e Épicos

A arquitetura e as entregas do projeto estão divididas nos seguintes pilares centrais:

* **[Épico 1: Controle de Acesso e Identidade](epicos/01-controle-de-acesso.md):** Sistema de cadastro e login seguro, garantindo que os usuários da comunidade sejam identificados para evitar spam e manter a confiabilidade dos registros.
* **[Épico 2: Motor Geoespacial e Visualização](epicos/02-mapa-interativo.md):** O coração da aplicação. Um mapa interativo e responsivo focado no consumo eficiente de coordenadas e na renderização de dados espaciais (estruturados em formatos como GeoJSON). Inclui a interface de busca, painéis de detalhes e aplicação de filtros dinâmicos.
* **[Épico 3: Gestão de Eventos](epicos/03-gestao-de-eventos.md):** Usuários cadastrados acessam e gerenciam eventos no mapa para divulgação centralizada e confiável de atividades no campus.
* **[Épico 4: Gestão de Problemas de Segurança](epicos/04-gestao-de-seguranca.md):** O sistema permite que usuários reportem problemas de segurança no campus com localização, imagens, tipo e prioridade, de forma identificada ou anônima, além de oferece acompanhamento por status, notificações, validação colaborativa, histórico de alterações e estatísticas para agilizar a solução e gerar confiança na plataforma.

## Requisitos Técnicos e Qualidade

A plataforma é construída sob premissas rigorosas para garantir uma experiência de alto nível.

> * [Requisitos Funcionais (RF)](requisitos/req-funcionais.md)

> * [Requisitos Não Funcionais (RNF)](requisitos/req-nao-funcionais.md)

**Resumo dos atributos de qualidade:**
* **Desempenho:** Tempos de resposta inferiores a 3 segundos para ações na interface.
* **Disponibilidade e Acessibilidade:** Operação 24 horas por dia com design responsivo (desktop e mobile) e interface intuitiva.
* **Segurança e Confiabilidade:** Armazenamento robusto e seguro, suportando o acesso simultâneo de múltiplos usuários da comunidade acadêmica.

