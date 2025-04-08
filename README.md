# 🐱 Galeria de Gatinhos com API + Bootstrap

Este projeto foi criado para **aprender a consumir uma API pública utilizando JavaScript**, e exibir as informações de forma bonita e responsiva com **Bootstrap**. É ideal para quem está começando agora no mundo da programação web.

Projeto na vercel: https://tela-consumo-api-gatinhos.vercel.app/

---

## 💡 O que é uma API?

API significa **Interface de Programação de Aplicações** (em inglês, *Application Programming Interface*).  
É uma forma de um site, aplicativo ou sistema **compartilhar informações com outros sistemas**.

Exemplo real:
- Quando você entra em um site de previsão do tempo, ele pega os dados de uma **API de clima**.
- Neste projeto, usamos uma **API de gatinhos**, que retorna **links de imagens de gatos aleatórios**.

---

## 🌐 O que é HTTP e o método `GET`?

Quando o navegador acessa um site ou uma API, ele se comunica com o servidor através do **protocolo HTTP**.

O método `GET` é usado para **pedir informações** para o servidor.  
No nosso caso, usamos `GET` para pedir imagens de gatinhos:

```
https://api.thecatapi.com/v1/images/search?limit=12
```

Esse link diz:
> Ei servidor, me mande 12 imagens de gatinhos 🐱

---

## 🧱 Estrutura do Projeto

```
consumo_api/
├── index.html        → Estrutura da página
├── css/
│   └── style.css     → Estilos personalizados
└── js/
    └── app.js        → Código JavaScript que busca os gatinhos
```

---

## 📄 index.html

- Usa **Bootstrap** para criar um layout bonito e responsivo.
- Possui:
  - Navbar (barra superior com o nome do site)
  - Header com título e descrição
  - Container onde as imagens vão aparecer
  - Footer com texto

```html
<div id="galeria" class="row g-4 justify-content-center">
  <!-- Aqui as imagens dos gatinhos serão inseridas via JavaScript -->
</div>
```

---

## 🧠 Como o JavaScript funciona?

No arquivo `js/app.js`, usamos `fetch()` para fazer uma **requisição HTTP GET** e buscar imagens da API.

```js
fetch('https://api.thecatapi.com/v1/images/search?limit=12')
  .then(res => res.json())
  .then(imagens => {
    imagens.forEach(img => {
      // Criamos dinamicamente os cards com as imagens dos gatinhos
    })
  })
  .catch(error => console.error('Erro ao carregar imagens', error))
```

### O que cada parte faz:

- `fetch(...)` → chama a API e pede os dados.
- `.then(res => res.json())` → converte a resposta em formato JSON (dados).
- `.then(imagens => { ... })` → usamos os dados recebidos para criar elementos no HTML.
- `.catch(...)` → se der erro (sem internet, API fora do ar), mostra no console.

---

## 📸 Exibindo as imagens com Bootstrap

Para cada imagem recebida da API, criamos um **card do Bootstrap** assim:

```html
<div class="card shadow-sm">
  <img src="URL_DA_IMAGEM" class="card-img-top" alt="Gatinho fofo" />
  <div class="card-body text-center">
    <p class="card-text">Esse gatinho é muito fofo!</p>
  </div>
</div>
```

Tudo isso é feito **automaticamente pelo JavaScript**, que monta os elementos e adiciona na `div` com ID `galeria`.

---

## 🎨 style.css

Arquivo simples para deixar o projeto mais bonito:
```css
body {
  background-color: #f8f9fa;
}

.card-img-top {
  height: 200px;
  object-fit: cover;
}
```

---

## 🚀 Como testar o projeto?

1. Baixe ou clone este repositório
2. Abra o arquivo `index.html` no navegador
3. Você verá 12 gatinhos sendo carregados automaticamente! 🐱

---

## 🤖 Curiosidade: esse projeto já usa um pouquinho de programação dinâmica!

Mesmo sem banco de dados ou backend, você já está usando **dados externos** e aprendendo **como a web realmente funciona**.

---

## 🙌 Próximo passo?

No próximo desafio, você vai aplicar esse mesmo conceito para exibir **notícias ao vivo**! 📰  
A ideia é exatamente a mesma — só muda a API e o tipo de dado.

---

## 📚 Recursos úteis para aprender mais

- [MDN Web Docs: fetch()](https://developer.mozilla.org/pt-BR/docs/Web/API/Fetch_API)
- [TheCatAPI - Documentação](https://thecatapi.com/)
- [Bootstrap 5 - Componentes](https://getbootstrap.com/docs/5.3/components/)
- [JSON - Explicação simples](https://www.devmedia.com.br/o-que-e-json/28486)

---

🧠 **Dica final:** Use o ChatGPT para tirar dúvidas! Pergunte coisas como:
> "Como fazer um card com Bootstrap?"  
> "Como consumir uma API com fetch?"  
> "Como manipular elementos com JavaScript?"

Aprender a perguntar é um superpoder de todo programador! 💪
