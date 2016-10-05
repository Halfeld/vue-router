# Primeiros Passos

> Nós vamos usar [ES2015](https://github.com/lukehoban/es6features) nos exemplos de código deste guia.

Criando um Single Page Application com Vue.js + vue-router é simples. Com Vue.js, nós já fazemos nossas aplicações com componentes. Quando adicionado o vue-router a mistura, todos nós precisamos mapear nossos componentes para as rotas e deixar o vue-router saber onde renderizar eles.
Aqui está um exemplo básico:

### HTML

``` html
<div id="app">
  <h1>Hello App!</h1>
  <p>
    <!-- use componente para navegação. -->
    <!-- especifique o link passando a prop `to`. -->
    <!-- <router-link> vai ser renderizado como um `<a>` tag por default. -->
    <router-link to="/foo">Go to Foo</router-link>
    <router-link to="/bar">Go to Bar</router-link>
  </p>
  <!-- saída da rota -->
  <!-- os componentes correspondentes vão ser renderizados aqui -->
  <router-view></router-view>
</div>
```

### JavaScript

``` js
// 0. Se estiver usando um sistema de modulos, chame `Vue.use(VueRouter)`

// 1. Defina os componentes nas rotas respectivas
// Estes podem ser importados de outros arquivos
const Foo = { template: '<div>foo</div>' }
const Bar = { template: '<div>bar</div>' }

// 2. Defina algumas rotas
// Cada rota deveria mapear para um component. O "componente" pode
// ser um construtor de componente real criado via
// Vue.extend(), ou só um objeto de opções de componente
// Nós vamos falar sobre rotas alinhadas depois.
const routes = [
  { path: '/foo', component: Foo },
  { path: '/bar', component: Bar }
]

// 3. Crie a intância da rota e passe a opção `routes`
// Você pode passar um opção adicional aqui, mais vamos
// manter simples agora.
const router = new VueRouter({
  routes // shorthand para `routes: routes`
})

// 4. Crie e monte a instância root
// Tenha certeza de injetar o router com as opções para fazer
// toda a app roteável
const app = new Vue({
  router
}).$mount('#app')

// Agora a app foi iniciada!
```

Você também pode checar este examplo [live](http://jsfiddle.net/yyx990803/xgrjzsup/).

Note que o `<router-link>` automaticamente pega a classe `.router-link-active` quando é alvo da rota correspondente. Você pode aprender mais sobre isso na [Referência da API](../api/router-link.md).
