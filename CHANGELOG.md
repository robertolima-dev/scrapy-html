# �� Changelog


## [1.4.0] - 2025-05-29
### Adicionado
- Novo módulo `validators` para validação e limpeza de dados HTML:
  - Limpeza de texto (`clean_text`)
  - Limpeza de HTML (`clean_html`)
  - Validação de URLs (`validate_url`)
  - Sanitização de atributos HTML (`sanitize_attributes`)
  - Extração de dados estruturados (meta tags, JSON-LD, Open Graph, Twitter Cards) (`extract_structured_data`)
- Testes automatizados para todas as funções de validação e limpeza
- Atualização do README com exemplos de uso do novo módulo
- Exportação da classe `DataValidator` no `__init__.py`

## [1.3.0] - 2025-05-06
### Adicionado
- Suporte a proxies HTTP/HTTPS
- Configuração de timeout para requisições via proxy

## [1.2.0] - 2025-04-29
### Adicionado
- Adicionamos suporte a múltiplos parsers HTML

## [1.1.5] - 2025-04-17
### Adicionado
- Passando headers como parametro

## [1.1.4] - 2025-02-25
### Adicionado
- Filtros por tags, classes e atributos

## [0.1.4] - 2025-02-24
### Adicionado
- Ajuste README

## [0.1.3] - 2025-02-24
### Adicionado
- Normalized name

## [0.1.2] - 2025-02-24
### Adicionado
- Ajuste README

## [0.1.1] - 2025-02-24
### Adicionado
- 🌟 Parâmetro `parser_type` para escolher o parser do BeautifulSoup.
- ⚡ Melhorias no tratamento de erros.

## [0.1.0] - 2025-02-24
### Adicionado
- 🚀 Primeira versão com scraping básico de HTML.
