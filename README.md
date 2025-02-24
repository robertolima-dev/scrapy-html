### 🚀 **README.md**

# 🌐 Scrapy-HTML

🔍 **Scrapy-HTML** é um pacote Python simples e eficiente que faz scraping do conteúdo HTML completo de qualquer página web fornecida. Ele utiliza as bibliotecas **BeautifulSoup4** e **Requests** para realizar a raspagem e retornar o HTML de forma estruturada e legível.

---

## ✨ **Características Principais**

- 🌎 Faz scraping de qualquer página web com uma URL válida.
- ⚡ Retorna o HTML formatado e legível usando `BeautifulSoup.prettify()`.
- 🔒 Tratamento de erros robusto para URLs inválidas ou problemas de rede.
- 💡 Leve e fácil de usar, com dependências mínimas.

---

## ⚡ **Instalação**

Para instalar o pacote diretamente do **PyPI**, execute:

```bash
pip install scrapy_html
```

---

## 💻 **Como Usar**

### 🔥 **Exemplo básico de uso:**
```python
from scrapy_html.scraper import get_html_content

# 🌐 URL da página que deseja raspar
url = "https://www.example.com"

# 🔄 Obtendo o conteúdo HTML da página
html = get_html_content(url)

# 📝 Exibindo o HTML formatado
print(html)
```

### 🔍 **Saída esperada:**
```html
<html>
  <head>
    <title>Example Domain</title>
  </head>
  <body>
    <div>
      <h1>Example Domain</h1>
      <p>This domain is for use in illustrative examples in documents.</p>
    </div>
  </body>
</html>
```

---

## 🛠 **Requisitos**

- Python >= 3.6
- [beautifulsoup4](https://pypi.org/project/beautifulsoup4/)
- [requests](https://pypi.org/project/requests/)

As dependências são instaladas automaticamente com o comando `pip install scrapy-html`.

---

## 🧪 **Testes**

Este projeto inclui testes básicos usando **pytest**. Para rodar os testes localmente:

```bash
pip install pytest
pytest tests/
```

---

## 🎨 **Recursos Futuros**

- [ ] 🌐 Suporte a diferentes parsers (`lxml`, `html5lib`).
- [ ] 🔄 Scraping assíncrono para maior desempenho.
- [ ] ⚡ Download de recursos estáticos (imagens, CSS, JS).
- [ ] 🎛 Parâmetros adicionais para scraping parcial.
- [ ] 🧪 Testes automatizados avançados com `requests-mock`.

---

## 🏗 **Estrutura do Projeto**

```
scrapy_html/
│
├── scrapy_html/             # 📦 Código principal
│   ├── __init__.py
│   └── scraper.py           # ⚡ Função principal do scraper
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
3. Faça suas alterações e faça commit:
   ```bash
   git commit -m "✨ Adicionando nova funcionalidade incrível"
   ```
4. Envie para o branch:
   ```bash
   git push origin minha-nova-funcionalidade
   ```
5. **Abra um Pull Request**. 💡

---

## 📝 **Licença**

Distribuído sob a **Licença MIT**. Veja o arquivo [LICENSE](LICENSE) para mais informações.

---

## 👨‍💻 **Autor**

Desenvolvido por **[Roberto Lima](https://robertolima-developer.vercel.app/)** 🚀✨

---

## 💬 **Contato**

- 📧 **Email**: robertolima.izphera@gmail.com
- 💼 **LinkedIn**: [Roberto Lima](https://www.linkedin.com/in/roberto-lima-01/)  

---

## ⭐ **Gostou do projeto?**

Deixe uma ⭐ no repositório e compartilhe com a comunidade! 🚀✨  
```

---

## 🌟 **O que este README oferece?**
- 🎯 **Descrição clara** do projeto e seu propósito.  
- 🛠 **Instruções detalhadas de instalação** e **uso prático**.  
- 🧪 **Guia de testes** para garantir que o código funciona.  
- 🏗 **Estrutura do projeto** para facilitar a navegação.  
- 🔄 **Seção de contribuição** para quem deseja ajudar no desenvolvimento.  
- 📝 **Licença e informações do autor** para transparência.
