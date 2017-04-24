# vue-pagination

> A pagination components for vue

> __NOTE:__  This component is just for vue 2+. Please check your Vue version first. 


## Demo

This project is a runtime demo. You can get the demo by these command:
```shell
git clone https://github.com/shangxinbo/vue-pagination.git yourPath
cd yourPath
npm install 
npm run dev  // serve with hot reload at http://localhost:8080 to see the demo 
```

If you want to build production with minification. you can do this:

```shell
npm run build
```

## Use

It's a **single-file component** for Vue.You should use it with webpack,babel and vue-loader to run.So I assume that you have node v4+ and npm v3+    

```shell
npm install --save shangxinbo/vue-pagination
```
then in your component,you can use it by this:
```javascript
import pages from 'vue-pagination'
export default {
    …
    components:{
        pages
    }
    …
}
```

## Docs

#### Props

- __total__

  type: Number

  desc: required is true, the max number of pages 

  e.g. : `123`

- __current__

  type: Number

  desc: required is true, the current page 

  e.g.:`23`

#### Events

- __jump(num)__

  triggler: clicke the page button or prev/next button

  num : return the num going to 
