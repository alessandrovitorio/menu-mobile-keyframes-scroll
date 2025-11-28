# 📘 Entendendo Animações com CSS e Eventos de Scroll em JavaScript

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


# ✅ **1. O que significa cada parte**

A propriedade `animation` é um **atalho** que combina várias outras propriedades.

Aqui está o significado:

| Valor        | Significado                                          |
| ------------ | ---------------------------------------------------- |
| **flip3d**   | nome dos `@keyframes` usados                         |
| **2s**       | duração da animação (vai de 0% a 100% em 2 segundos) |
| **linear**   | tipo da curva de aceleração                          |
| **infinite** | a animação repete para sempre                        |

---

# 🎯 **2. Todas as propriedades que cabem dentro do shorthand**

O `animation:` pode conter até **8 propriedades**:

```css
animation: 
  name 
  duration 
  timing-function 
  delay 
  iteration-count 
  direction 
  fill-mode 
  play-state;
```

### Exemplo COMPLETO:

```css
animation: flip3d 2s ease-in-out 0.5s infinite alternate both running;
```

---

# 🧠 **3. Explicação de cada uma**

---

## **✔ animation-name**

Nome dos keyframes:

```css
animation-name: flip3d;
```

---

## **✔ animation-duration**

Quanto tempo dura:

```css
animation-duration: 2s; /* pode ser 200ms, 10s... */
```

---

## **✔ animation-timing-function**

Define como a animação acelera:

### Valores mais usados:

* `linear` — velocidade constante
* `ease` — padrão (começa lento, acelera, termina lento)
* `ease-in` — começa devagar
* `ease-out` — termina devagar
* `ease-in-out` — início e fim suaves
* `steps(4)` — anima por “degraus” (tipo sprite)
* `cubic-bezier(.17, .67, .83, .67)` — curva personalizada

---

## **✔ animation-delay**

Tempo antes da animação começar:

```css
animation-delay: 0.5s;
```

---

## **✔ animation-iteration-count**

Quantas vezes repete:

```css
animation-iteration-count: infinite;
```

Outros valores:

* `1` (padrão)
* `3` (repete 3 vezes)
* `infinite` (loop eterno)

---

## **✔ animation-direction**

Como a animação se comporta a cada ciclo:

### Valores:

* `normal` — vai de 0% → 100%
* `reverse` — vai de 100% → 0%
* `alternate` — vai e volta (0→100→0→100)
* `alternate-reverse` — igual mas começando do fim

---

## **✔ animation-fill-mode**

Define o estilo antes/depois do fim da animação:

* `none` — nada muda
* `forwards` — mantém o estado final do keyframe
* `backwards` — usa estado inicial durante o delay
* `both` — combina os dois

---

## **✔ animation-play-state**

Controla se está rodando ou pausada:

```css
animation-play-state: paused;
animation-play-state: running;
```

---

# 🌟 **4. Exemplos com diferentes possibilidades**

### 🔁 **Vai e volta devagar**

```css
animation: flip3d 2s ease-in-out infinite alternate;
```

### 🎞 **Em etapas (efeito de sprites)**

```css
animation: flip3d 1s steps(4) infinite;
```

### 🐢 **Começa depois de 1 segundo**

```css
animation: flip3d 2s linear 1s infinite;
```

### 🚀 **Vai extremamente rápido**

```css
animation: flip3d 300ms linear infinite;
```

### 🧊 **Mantém a posição final**

```css
animation: flip3d 2s linear infinite forwards;
```

---

# 💡 Resumo didático

```
animation: (nome) (duração) (curva) (delay) (quantas vezes) 
           (direção) (fill-mode) (estado-play);
```

Você pode usar **todos**, ou só **alguns** — o CSS entende.



