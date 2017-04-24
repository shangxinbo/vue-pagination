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

  type: String

  desc: init value for input and datetimepicker.__note that if you set `format`prop, this value must apply to your format__

  e.g. : `'2017-11-23'`

- __current__

  type: Object

  desc: you can set this value to customize the view of picker.This object support three available keys.

  - header    : background-color for header (year and month) 
  - headerText : color for the font in header (year and month)
  - checkedDate : background-color for selected day

  e.g.:

  ```javascript
  {
    header:'#cccccc',
    headerText:'blue',
    checkedDate:'green'
  }
  ```

#### Events

- __jump(value)__

  triggler: when choose the date or time (click ok buttons).when the input value changed

  value : return the picked value that formatted by your format option 
