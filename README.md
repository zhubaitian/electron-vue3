# electron-vue3

Electron vue3 boilerplate with router-view support

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run electron:serve
```

### Compiles and minifies for production
```
npm run electron:build
```

## Notes

### File Structure
- @/background.ts: Main process
- @/views/: Renderer process implemeted with Vue3.x support, our works should be focus on implementing our businiess logic under this folder
- @/App.vue: Support router view, so that we could use router.push() and related functions in our vue files 
- @/router/index.ts: Router definition file
- @/store/: vuex store. todo: replace vuex with pinia
- @preload/: todo: preload related features support

## Q&A

### error: loaderContext.getOptions is not a function

https://stackoverflow.com/questions/68016372/webpack-ts-loader-error-loadercontext-getoptions-is-not-a-function

```
npm install ts-loader@~8.2.0
```