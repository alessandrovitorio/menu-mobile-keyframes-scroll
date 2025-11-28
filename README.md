# 📘 README – Entendendo Animações com CSS e Eventos de Scroll em JavaScript

Este projeto foi criado com o objetivo de **ensinar conceitos fundamentais de animação em CSS** e o **uso do evento de scroll no JavaScript**, integrando front-end moderno de maneira prática e visual.

---

## 🎨 1. Animação com CSS Keyframes

### 🔹 O que é `@keyframes`?

`@keyframes` é um recurso do CSS que permite criar **animações personalizadas**, definindo passo a passo como um elemento vai mudar ao longo do tempo.

No projeto, ele foi usado para **animar o gradiente de cor do texto**, criando um efeito vibrante e moderno.

### 🔹 Como funciona no código

```css
@keyframes gradientMove {
  0% { background-position: 0%; }
  25% { background-position: 50%; }
  50% { background-position: 100%; }
  75% { background-position: 50%; }
  100% { background-position: 0%; }
}
```

✔ O gradiente vai se movimentando horizontalmente.
✔ Ele cria o “vai e volta” suave das cores.
✔ A animação é aplicada com:

```css
animation: gradientMove 9s ease infinite;
```

---

## 🌈 2. Uso de `background-clip: text`

O texto “ALEDEV” recebe um degradê animado **dentro das letras**.

Isso é feito com:

```css
-webkit-background-clip: text;
background-clip: text;
color: transparent;
```

### O que isso faz?

* O texto vira uma **máscara**.
* O background (o gradiente) aparece **apenas dentro das letras**.
* O texto fica com um visual moderno, muito usado em sites profissionais.

---

## 🧭 3. Cabeçalho com efeito ao rolar a página (scroll)

O JavaScript adiciona dinamismo ao site detectando quando o usuário rola a página.

### Código

```javascript
window.addEventListener("scroll", () => {
  const header = document.querySelector("header");

  if (window.scrollY > 50) {
    header.classList.add("scrolled");
  } else {
    header.classList.remove("scrolled");
  }
});
```

### 🔹 Conceito importante: `scroll`

`window.addEventListener("scroll")` permite que o site **reaja ao movimento de rolagem do usuário**, ativando comportamentos dinâmicos como:

* mudar o fundo do header
* adicionar efeitos de blur
* criar menus que aparecem e desaparecem

### 🔹 O que a classe `.scrolled` faz?

```css
header.scrolled {
  background: rgba(0, 0, 0, 0.557);
  backdrop-filter: blur(6px);
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
  border-bottom: #5b5be7 4px solid;
}
```

✔ O header ganha um fundo escuro com transparência
✔ Um efeito de **desfoque (blur)** é aplicado
✔ Um **shadow leve** é adicionado
✔ A borda inferior aparece em azul roxo

O resultado é um **menu fixo moderno, estiloso e responsivo**, muito usado em sites profissionais.

---

## 🧑‍🏫 4. Objetivo Educacional

Esse exemplo ensina os alunos a:

### ✔ Entender e aplicar animações com keyframe

### ✔ Criar textos com degradê animado

### ✔ Manipular classes com JavaScript

### ✔ Aprender o uso prático de `addEventListener("scroll")`

### ✔ Criar um header fixo com comportamento inteligente

### ✔ Integrar HTML + CSS + JS de forma moderna

Isso fornece base para criar:

* efeitos visuais profissionais
* animações de interface
* menus reativos
* experiências de navegação compostas
