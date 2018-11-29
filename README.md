# nuxt-apollo-crash
Issue reproduction:  
Using @nuxtjs/apollo, Nuxt server crashes when some apollo user custom function throw an error.  



Files of interest:
* pages/index.vue
* nuxt.config.js (apollo module declaration and configuration)s

## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).
