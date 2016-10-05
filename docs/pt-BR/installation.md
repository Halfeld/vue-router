# Installation

### Download Direto/ CDN

[https://unpkg.com/vue-router](https://unpkg.com/vue-router)

[Unpkg.com](https://unpkg.com) provê links da CDN baseado no NPM. O link acima vai sempre apontar para o ultimo lançamento do NPM. Você consegue também especificar a versão/tag por URLs como `https://unpkg.com/vue-router@2.0.0`.

Inclua sempre o Vue Router depois do vue e ele vai se instalar automaticamente.

``` html
<script src="/path/to/vue.js"></script>
<script src="/path/to/vue-router.js"></script>
```

### NPM

``` bash
npm install vue-router
```

Quando usado com um sistema de modulo, você precisa explicitamente instalar o router com `Vue.use()`;

``` js
import Vue from 'vue'
import VueRouter from 'vue-router'

Vue.use(VueRouter)
```

Você não precisa fazer isso quando usado globalmente como no caso das tags script.

### Dev Build

Você vai ter que clonar diretamente do Github e fazer a Build do `vue-router` se você quiser usar a ultima versão de desenvolvimento.

``` bash
git clone https://github.com/vuejs/vue-router.git node_modules/vue-router
cd node_modules/vue-router
npm install
npm run build
```
