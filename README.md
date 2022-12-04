# myapp

## Project setup
```
npm install
```

## Install Vuetify3
```
npm install vuetify@^3.0.3
```
```
main.ts

import { createApp } from 'vue'
import App from './App.vue'

// Vuetify
import 'vuetify/styles'
import { createVuetify } from 'vuetify'
import * as components from 'vuetify/components'
import * as directives from 'vuetify/directives'

const vuetify = createVuetify({
  components,
  directives,
})

createApp(App).use(vuetify).mount('#app')
```

## Install mdi
```
npm i -D @mdi/js
```
```
main.ts 

add: import "@mdi/font/css/materialdesignicons.css";
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
