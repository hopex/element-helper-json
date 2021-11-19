### vscode-element-helper直接替换自己的json数据
```javascript
//vscode-element-helper/src/app.ts
//json数据替换为自己的
import * as kebabCaseTAGS from 'element-helper-json-new/element-tags.json';
import * as kebabCaseATTRS from 'element-helper-json-new/element-attributes.json';
```
### 替换掉vscode-element-helper插件中node_modules的element-helper-json-new的json数据
```javascript
//elemefe.vscode-element-helper-0.5.6\node_modules\element-helper-json-new\element-tags.json
//elemefe.vscode-element-helper-0.5.6\node_modules\element-helper-json-new\element-attributes.json
```

### 快速手动提取新组件属性
```javascript
//<script src="https://cdn.jsdelivr.net/npm/humps@2.0.1/humps.min.js"></script>
//<script src="https://cdn.jsdelivr.net/npm/element-ui@2.15.7/lib/index.min.js"></script>
//<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/element-ui@2.15.7/lib/theme-chalk/index.min.css" />
//<script src="https://cdn.jsdelivr.net/npm/vue@2.6.11/dist/vue.js"></script>

const getProps=(comp)=>{
  return JSON.stringify({
     [humps.decamelize(comp.name, { separator: '-' })]:{
            "attributes":Object.keys(comp.props).map(m=>humps.decamelize(m, { separator: '-' })),
            "subtags": [],
            "new-component":true
     }
  })
}

//use
getProps(ELEMENT.Button)
```
