# 🍰 Doces Manhãs — Cardápio Digital PWA

Cardápio digital da **Doces Manhãs Confeitaria**. Permite que clientes escolham produtos, montem o carrinho e enviem o pedido formatado direto pelo WhatsApp — sem chatbot, sem app para instalar.

---

## Estrutura do projeto

```
doces-manhas/
├── index.html      ← Toda a aplicação (HTML + CSS + JS)
├── manifest.json   ← Configuração PWA
├── sw.js           ← Service Worker (funciona offline)
├── icons/
│   ├── icon-192.png  ← Logo 192×192px
│   └── icon-512.png  ← Logo 512×512px
└── README.md
```

---

## Como publicar no GitHub Pages (gratuito)

1. Crie um repositório no GitHub (ex: `doces-manhas`)
2. Faça upload de todos os arquivos
3. Vá em **Settings → Pages**
4. Em *Branch*, selecione `main` e clique **Save**
5. Aguarde 1–2 minutos — o link ficará no formato:
   ```
   https://SEU_USUARIO.github.io/doces-manhas/
   ```

---

## Como atualizar os produtos

Abra o `index.html` e edite o array `products` a partir da linha com `// CONFIGURAÇÃO`:

```js
const products = [
  {
    id: 1,
    name: "Nome do produto",
    desc: "Descrição curta",
    price: 85,          // preço em reais (número)
    emoji: "🎂",        // emoji representativo
    cat: "bolos",       // bolos | tortas | doces | brownie | kit
    highlight: true,    // true = aparece em destaque (só 1 por vez)
    badge: ""           // "novo" | "combo" | "" (vazio = sem badge)
  },
  // ... outros produtos
];
```

---

## Como trocar o número do WhatsApp

Na mesma seção `// CONFIGURAÇÃO`, altere:

```js
const PHONE = '5521997940370'; // apenas números, com código do país
```

---

## Como adicionar as categorias

Edite os botões na seção `<!-- CATEGORIES -->` do HTML:

```html
<button class="cat" onclick="filterCat('nova-categoria', this)">Nova Categoria</button>
```

E nos produtos, use `cat: "nova-categoria"`.

---

## Ícones (importante para PWA)

A pasta `icons/` precisa ter:
- `icon-192.png` — versão 192×192px da logo
- `icon-512.png` — versão 512×512px da logo

Você pode gerar essas versões em [realfavicongenerator.net](https://realfavicongenerator.net).

---

## Funcionalidades

- ✅ Cardápio em grade Bento Grid
- ✅ Busca por nome/descrição
- ✅ Filtro por categorias
- ✅ Carrinho com controle de quantidade
- ✅ Pedido enviado via WhatsApp já formatado
- ✅ PWA — pode ser instalado como app no celular
- ✅ Funciona offline (Service Worker)
- ✅ Responsivo para mobile

---

Desenvolvido por **Alessandro** para a Doces Manhãs Confeitaria.
