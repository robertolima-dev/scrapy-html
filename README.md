### 🚀 **README.md**

# 🌐 Scrapy-HTML

🔍 **Scrapy-HTML** é um pacote Python simples e eficiente para scraping de conteúdo HTML de qualquer página web. Agora com **parâmetros avançados** para filtragem por tag, múltiplas tags, classe CSS e atributos personalizados, tornando a raspagem muito mais flexível e poderosa. Ele utiliza as bibliotecas **BeautifulSoup4** e **Requests** para realizar a raspagem e retornar o HTML de forma estruturada e legível.

---

## ✨ **Características Principais**

- 🌎 Faz scraping de qualquer página web com uma URL válida.
- 🔍 **Filtragem avançada** por:
  - Tag única (`tag`)
  - Múltiplas tags (`tags`)
  - Classe CSS (`class_`)
  - ID (`id_`)
  - Atributos personalizados (`attrs`)
  - Headers HTTP personalizados (`headers`)
- 🌐 **Suporte a Proxies**:
  - Configuração de proxies HTTP/HTTPS
  - Timeout personalizado para requisições via proxy
- ⚡ **Múltiplos parsers HTML**:
  - `html.parser` (padrão): Parser nativo do Python
  - `lxml`: Parser rápido baseado em C
  - `html5lib`: Parser mais leniente e compatível com HTML5
- ⚡ Retorna o HTML formatado e legível usando `BeautifulSoup`.
- 🔒 Tratamento de erros robusto para URLs inválidas ou problemas de rede.
- 💡 Leve e fácil de usar, com dependências mínimas.
- 🧹 **Validação e Limpeza de Dados**:
  - Limpeza de texto e HTML
  - Validação de URLs
  - Sanitização de atributos HTML
  - Extração de dados estruturados (meta tags, JSON-LD, Open Graph, Twitter Cards)

---

## ⚡ **Instalação**

Instale o pacote diretamente do **PyPI**:

```bash
pip install scrapy_html
```

### 📦 **Parsers Opcionais**

Para usar parsers alternativos, instale as dependências opcionais:

```bash
# Para usar o parser lxml (mais rápido)
pip install scrapy_html[lxml]

# Para usar o parser html5lib (mais leniente)
pip install scrapy_html[html5lib]

# Para usar todos os parsers
pip install scrapy_html[lxml,html5lib]
```

---

## 💻 **Como Usar**

### 🔥 **Exemplo básico de uso:**
```python
from scrapy_html.scraper import get_html_content

# 🌐 URL da página
url = "https://www.example.com"

# 🔄 Obtendo o conteúdo HTML completo
dados = get_html_content(url)
print(dados)
```

### 🎯 **Filtragem Avançada:**

#### 🔍 **Filtrar por tag única:**
```python
dados = get_html_content(url, tag="p")
print(dados)  # Exibe todas as tags <p>
```

#### 🏷 **Filtrar por múltiplas tags:**
```python
dados = get_html_content(url, tags="div,span")
print(dados)  # Exibe todas as tags <div> e <span>
```

#### 🎨 **Filtrar por classe CSS:**
```python
dados = get_html_content(url, tag="a", class_="link-destaque")
print(dados)
```

#### 🆔 **Filtrar por ID:**
```python
dados = get_html_content(url, tag="section", id_="conteudo-principal")
print(dados)
```

#### 🛠 **Filtrar por atributos personalizados:**
```python
dados = get_html_content(url, tag="img", attrs={"alt": "Imagem principal"})
print(dados)
```

#### 🔒 **Usar headers personalizados:**
```python
headers = {
    "User-Agent": "Mozilla/5.0",
    "Accept": "text/html",
    "Accept-Language": "pt-BR"
}
dados = get_html_content(url, headers=headers)
print(dados)
```

#### 🔍 **Usar diferentes parsers HTML:**
```python
# Usando o parser padrão (html.parser)
dados = get_html_content(url)
print(dados)

# Usando o parser lxml (mais rápido)
dados = get_html_content(url, parser="lxml")
print(dados)

# Usando o parser html5lib (mais leniente)
dados = get_html_content(url, parser="html5lib")
print(dados)
```

#### 🌐 **Usar proxies:**
```python
proxies = {
    "http": "http://proxy1:8080",
    "https": "https://proxy2:8080"
}
dados = get_html_content(
    url,
    proxies=proxies,
    proxy_timeout=30  # timeout em segundos
)
print(dados)
```

### 🧹 **Validação e Limpeza de Dados:**

```python
from scrapy_html import DataValidator

validator = DataValidator()

# Limpeza de texto
texto_limpo = validator.clean_text("  Hello   World  ")
print(texto_limpo)  # "Hello World"

# Limpeza de HTML
html_limpo = validator.clean_html("<script>alert('test');</script><p>Hello</p>")
print(html_limpo)  # "<p>Hello</p>"

# Validação de URL
url_valida = validator.validate_url("http://example.com")
print(url_valida)  # True

# Sanitização de atributos
from bs4 import BeautifulSoup
html = '<a href="http://example.com" onclick="alert(1)">Link</a>'
soup = BeautifulSoup(html, 'html.parser')
tag = soup.find('a')
tag_sanitizada = validator.sanitize_attributes(tag)
print(tag_sanitizada)  # <a href="http://example.com">Link</a>

# Extração de dados estruturados
dados = validator.extract_structured_data("""
    <meta name="description" content="Test">
    <meta property="og:title" content="Test OG">
    <script type="application/ld+json">
        {"@type": "WebPage"}
    </script>
""")
print(dados)  # {'meta': {'description': 'Test'}, 'open_graph': {'title': 'Test OG'}, ...}
```

---

## 🛠 **Requisitos**

- Python >= 3.6
- [beautifulsoup4](https://pypi.org/project/beautifulsoup4/)
- [requests](https://pypi.org/project/requests/)

As dependências são instaladas automaticamente com:

```bash
pip install scrapy_html
```

---

## 🧪 **Testes**

Este projeto inclui testes usando **pytest**. Para rodar os testes localmente:

```bash
pip install pytest
pytest tests/
```

---

## 🎨 **Recursos Futuros**

- [x] 🔍 Parâmetros avançados para scraping filtrado.
- [x] 🌐 Suporte a diferentes parsers (`lxml`, `html5lib`).
- [x] 🌐 Suporte a proxies HTTP/HTTPS.
- [ ] 🔄 Scraping assíncrono para maior desempenho.
- [ ] ⚡ Download de recursos estáticos (imagens, CSS, JS).
- [ ] 🧪 Testes automatizados avançados com `requests-mock`.

---

## 🏗 **Estrutura do Projeto**

```
scrapy_html/
│
├── scrapy_html/             # 📦 Código principal
│   ├── __init__.py
│   └── scraper.py           # ⚡ Função principal: get_html_content()
│
├── tests/                   # 🧪 Testes automatizados
│   └── test_scraper.py
│
├── setup.py                 # ⚙️ Configuração para PyPI
├── pyproject.toml           # 📦 Configuração moderna
├── README.md                # 📚 Documentação do projeto
├── LICENSE                  # 📜 Licença MIT
└── MANIFEST.in              # 📋 Inclusão de arquivos extras
```

---

## 🔧 **Contribuindo**

Contribuições são bem-vindas! 🚀  
Para contribuir, siga estas etapas:

1. **Fork** este repositório.
2. Crie uma nova branch:
   ```bash
   git checkout -b minha-nova-funcionalidade
   ```
3. Faça suas alterações e commit:
   ```bash
   git commit -m "✨ Adicionando nova funcionalidade incrível"
   ```
4. Envie para o branch:
   ```bash
   git push origin minha-nova-funcionalidade
   ```
5. **Abra um Pull Request**. 💡

---

## 👨‍💻 **Autor**

Desenvolvido por **[Roberto Lima](https://github.com/robertolima-dev)** 🚀✨

---

## 💬 **Contato**

- 📧 **Email**: robertolima.izphera@gmail.com
- 💼 **LinkedIn**: [Roberto Lima](https://www.linkedin.com/in/roberto-lima-01/)
- 💼 **Website**: [Roberto Lima](https://robertolima-developer.vercel.app/)
- 💼 **Gravatar**: [Roberto Lima](https://gravatar.com/deliciouslyautomaticf57dc92af0)


---

## 📄 Licença
MIT License
