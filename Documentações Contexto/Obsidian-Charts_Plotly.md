# Combined Code Export

**Data de criação:** 2025-11-16 23:19:59
**Total de arquivos:** 10

---

---
## README.md

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\README.md`
- **Tamanho:** 3.4 KB
- **Linhas:** 83
- **Caracteres:** 3435
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```markdown
   1 | # obsidian-plotly
   2 | Obsidian plugin, which allow user to embed Plotly charts into markdown notes.
   3 | 
   4 | # Usage
   5 | ## Basic (using plotly block)
   6 | Use Command Palette (`Ctrl-P`) to add basic plotly template: 
   7 | ![Command example](./media/plotly-command-demo.gif)
   8 | 
   9 | This approach allows you to create JSON or YAML inside `plotly` block 
  10 | with payload for data, layout and config objects. 
  11 | It does NOT support JavaScript examples from plotly.com site - it only support static payload forvarding to `Plotly.newPlot` function.
  12 | For JavaScript support use Advanced approach with DataViewJS.
  13 | 
  14 | Basic example (those YAML and JSON result in identical plots):
  15 | ```yaml
  16 |     ```plotly
  17 |     data:
  18 |     	- x: [0,1,2]
  19 |     	  y: [0,1,0]
  20 |     ```
  21 | ```
  22 | 
  23 | ```json
  24 |     ```plotly
  25 |     {
  26 |         "data": [{
  27 |             "x":[0, 1, 2],
  28 |             "y":[0, 1, 0]
  29 |         }]
  30 |     }
  31 |     ```
  32 | ```
  33 | 
  34 | ## Advanced (using dataviewjs block)
  35 | Use Command Palette (`Ctrl-P`) to add plotly template: 
  36 | ![Command example](./media/plotly-dataviewjs-command-demo.gif)
  37 | 
  38 | This approach DOES support any example from plotly.com. 
  39 | (I haven't checked them all, feel free to create issue if some aren't working).
  40 | However, this approach require DataView plugin to process JavaScript.
  41 | As a benefit, you can create plots based on data from you notes which you retrieve via DataView API!
  42 | (By the way, this sounds similar to what [obsidian-tracker](https://github.com/pyrochlore/obsidian-tracker) plugin does).
  43 | 
  44 | To use it, just add DataviewJS block with Plotly command, copy desired example and paste it.
  45 | NOTE: All examples use `Plotly.newPlot(component, data, layout, config)` to draw, and it takes some extra code to work in Obsidian.
  46 | There is a wrapper function available as `window.renderPlotly(this.component, data, layout, config)`, which will draw plot inside DataViewJS block.
  47 | (Wrapper parameters should be same as in example).
  48 | 
  49 | A lot of examples are on [Plotly](https://plotly.com/javascript/) official site.
  50 | 
  51 | ![How to copy examples from plotly.com](./media/plotly-copy-from-examples-demo.gif)
  52 | 
  53 | NOTE: Some examples also require d3 library. This is large library and rarely needed. That's why I do not want to have it in plugin.
  54 | If you need this library, there is a workaround: you can download d3 library from official [site](https://d3js.org/d3.v7.min.js) (Open link->Right click->Save as...), place it in your vault and import using `require`; 
  55 | 
  56 | ```js
  57 |     ```dataviewjs
  58 |         //Some plotly examples require d3 library to work.
  59 |         //Since it's large and used by few examples,
  60 |         //I propose a workaround to import d3;
  61 |         //You need to download dependency from https://d3js.org/d3.v7.min.js
  62 |         //and place it in your vault.
  63 |         let path = app.vault.adapter.basePath;//absolute path to your vault
  64 |         var d3 = require(path+"\\utils\\d3.v7.min.js");
  65 | 
  66 |         //Replace this block with any example from plotly.com
  67 |         //NOTE: `Plotly.newPlot` won't work here, use `window.renderPlotly` instead
  68 |         var data = [
  69 |             {x:[0,1,2,3,4,5,6,7,8,9],y:[4,4,2,2,3,3,2,2,4,4]},
  70 |             {x:[0,1,2,3,4,5,6,7,8,9],y:[3,3,1,1,2,2,1,1,3,3]}
  71 |         ];
  72 |         var layout = {title:"Example in DataViewJS"};
  73 |         var config = {displaylogo:false};
  74 | 
  75 |         window.renderPlotly(this.container, data, layout, config)
  76 |     ```
  77 | ```
  78 | 
  79 | # Examples
  80 | Some more obsidian examples of this plugin [here](examples.md)
  81 | 
  82 | More examples on [Plotly](https://plotly.com/javascript/) official site.
  83 | 
```

---
## examples.md

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\examples.md`
- **Tamanho:** 6.6 KB
- **Linhas:** 268
- **Caracteres:** 6759
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```markdown
   1 | ---
   2 | dataX: [0,2,3,4,6,8,9,10,13,14]
   3 | dataY: [0,10, 20, 30, 40, 50, 60, 70, 80, 90]
   4 | 
   5 | pievalues: [12, 20, 50, 30]
   6 | ---
   7 | 
   8 | # Welcome to some examples
   9 | By Damon-Lee Pointon
  10 | 
  11 | Throw this file into your vault (by downloading the examples.md file as Raw) of choice and make sure you have atleast Dataview and of course this obsidian-plotly plugin installed and running.
  12 | 
  13 | Dependant on your system you may have to change the back slash with a forward slash. I'm using a Mac so backslashes are the norm.
  14 | 
  15 | When combining the obsidian-plotly plugin with dataviewjs and yaml. You will need you include: `let pg = dv.current()` and then if your yaml field is `dataX` then you need to use `pg.dataX.values` when you want to refer to it inside the dataviewjs code block. This will be seen as an example in the below Line Plot and Pie Chart sections.
  16 | 
  17 | Please note that my `d3.v7.min.js` is in the main vault not the utils folder... mainly because I can't find it.
  18 | 
  19 | # Line Plot
  20 | Found [here](https://plotly.com/javascript/line-charts/#basic-line-plot)
  21 | ```dataviewjs
  22 | let pg = dv.current()
  23 | let path = app.vault.adapter.basePath;
  24 | var d3 = require(path+"//d3.v7.min.js");
  25 | console.log(d3)
  26 | 
  27 | var data = [
  28 |  {x: pg.dataX.values,y: pg.dataY.values}
  29 | ];
  30 | var layout = {title:"Example in DataViewJS"};
  31 | var config = {displaylogo:false};
  32 | 
  33 | window.renderPlotly(this.container, data, layout, config)
  34 | ```
  35 | 
  36 | # Scatter Plot
  37 | Found [here](https://plotly.com/javascript/line-and-scatter/#line-and-scatter-plot)
  38 | ```dataviewjs
  39 | let path = app.vault.adapter.basePath;
  40 | var d3 = require(path+"//d3.v7.min.js");
  41 | 
  42 | var trace1 = {
  43 |   x: [1, 2, 3, 4],
  44 |   y: [10, 15, 13, 17],
  45 |   mode: 'markers',
  46 |   type: 'scatter'
  47 | };
  48 | 
  49 | var trace2 = {
  50 |   x: [2, 3, 4, 5],
  51 |   y: [16, 5, 11, 9],
  52 |   mode: 'lines',
  53 |   type: 'scatter'
  54 | };
  55 | 
  56 | var trace3 = {
  57 |   x: [1, 2, 3, 4],
  58 |   y: [12, 9, 15, 12],
  59 |   mode: 'lines+markers',
  60 |   type: 'scatter'
  61 | };
  62 | 
  63 | var data = [trace1, trace2, trace3];
  64 | 
  65 | var layout = {
  66 |   xaxis: {range: [ 0, 5 ]},
  67 |   yaxis: {range: [0, 20]},
  68 |   title:'Data Labels Hover'
  69 | };
  70 | 
  71 | window.renderPlotly(this.container, data, layout)
  72 | 
  73 | ```
  74 | 
  75 | # Pie Chart
  76 | Found [here](https://plotly.com/javascript/pie-charts/#basic-pie-chart).
  77 | ```dataviewjs
  78 | let pg = dv.current()
  79 | let path = app.vault.adapter.basePath;
  80 | var d3 = require(path+"//d3.v7.min.js");
  81 | console.log(d3)
  82 | 
  83 | var data = [{
  84 |  values: pg.pievalues.values,
  85 |  labels: ['Pizza', 'Quark', 'Vegatables', 'Fruit'],
  86 |  type: 'pie'
  87 |  }];
  88 | var layout = {title:"Food this week"};
  89 | var config = {displaylogo:false};
  90 | 
  91 | window.renderPlotly(this.container, data, layout, config)
  92 | ```
  93 | 
  94 | # Heatmap
  95 | Found [here](https://plotly.com/javascript/heatmaps/#basic-heatmap).
  96 | ```dataviewjs
  97 | let path = app.vault.adapter.basePath;
  98 | var d3 = require(path+"//d3.v7.min.js");
  99 | console.log(d3)
 100 | 
 101 | var data = [
 102 |  {
 103 |     z: [[1, null, 30, 50, 1], [20, 1, 60, 80, 30], [30, 60, 1, -10, 20]],
 104 |     x: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'],
 105 |     y: ['Morning', 'Afternoon', 'Evening'],
 106 |     type: 'heatmap',
 107 |     hoverongaps: false
 108 |   }
 109 | ];
 110 | 
 111 | var layout = {title:"Example Heatmap w/ DataViewJS"};
 112 | var config = {displaylogo:false};
 113 | 
 114 | window.renderPlotly(this.container, data, layout, config)
 115 | ```
 116 | 
 117 | # Annotated Heatmap
 118 | Found [here](https://plotly.com/javascript/heatmaps/#annotated-heatmap).
 119 | ```dataviewjs
 120 | let path = app.vault.adapter.basePath;
 121 | var d3 = require(path+"//d3.v7.min.js");
 122 | console.log(d3)
 123 | 
 124 | var xValues = ['A', 'B', 'C', 'D', 'E'];
 125 | 
 126 | var yValues = ['W', 'X', 'Y', 'Z'];
 127 | 
 128 | var zValues = [
 129 |   [0.00, 0.00, 0.75, 0.75, 0.00],
 130 |   [0.00, 0.00, 0.75, 0.75, 0.00],
 131 |   [0.75, 0.75, 0.75, 0.75, 0.75],
 132 |   [0.00, 0.00, 0.00, 0.75, 0.00]
 133 | ];
 134 | 
 135 | var colorscaleValue = [
 136 |   [0, '#3D9970'],
 137 |   [1, '#001f3f']
 138 | ];
 139 | 
 140 | var data = [{
 141 |   x: xValues,
 142 |   y: yValues,
 143 |   z: zValues,
 144 |   type: 'heatmap',
 145 |   colorscale: colorscaleValue,
 146 |   showscale: false
 147 | }];
 148 | 
 149 | var layout = {
 150 |   title: 'Annotated Heatmap',
 151 |   annotations: [],
 152 |   xaxis: {
 153 |     ticks: '',
 154 |     side: 'top'
 155 |   },
 156 |   yaxis: {
 157 |     ticks: '',
 158 |     ticksuffix: ' ',
 159 |     width: 700,
 160 |     height: 700,
 161 |     autosize: false
 162 |   }
 163 | };
 164 | 
 165 | for ( var i = 0; i < yValues.length; i++ ) {
 166 |   for ( var j = 0; j < xValues.length; j++ ) {
 167 |     var currentValue = zValues[i][j];
 168 |     if (currentValue != 0.0) {
 169 |       var textColor = 'white';
 170 |     }else{
 171 |       var textColor = 'black';
 172 |     }
 173 |     var result = {
 174 |       xref: 'x1',
 175 |       yref: 'y1',
 176 |       x: xValues[j],
 177 |       y: yValues[i],
 178 |       text: zValues[i][j],
 179 |       font: {
 180 |         family: 'Arial',
 181 |         size: 12,
 182 |         color: 'rgb(50, 171, 96)'
 183 |       },
 184 |       showarrow: false,
 185 |       font: {
 186 |         color: textColor
 187 |       }
 188 |     };
 189 |     layout.annotations.push(result);
 190 |   }
 191 | }
 192 | 
 193 | window.renderPlotly(this.container, data, layout)
 194 | ```
 195 | 
 196 | 
 197 | # Waterfall
 198 | Found [here](https://plotly.com/javascript/waterfall-charts/#basic-waterfall-chart).
 199 | ```dataviewjs
 200 | 
 201 | let path = app.vault.adapter.basePath;
 202 | var d3 = require(path+"//d3.v7.min.js");
 203 | console.log(d3)
 204 | 
 205 | var data = [
 206 |         {name: "2018",
 207 |          type: "waterfall",
 208 |          orientation: "v",
 209 |          measure: ["relative","relative",
 210 |                 "total","relative",
 211 |                 "relative","total"],
 212 |          x: ["Sales","Consulting","Net revenue",
 213 | 		     "Purchases","Other expenses","Profit before tax"],
 214 |          textposition: "outside",
 215 |          text: ["+60","+80","","-40","-20","Total"],          
 216 |          y: [60,80,0,-40,-20,0],
 217 |          connector: {
 218 | 		     line: {color: "rgb(63, 63, 63)"}
 219 |              },
 220 |          }
 221 |     ];
 222 | 	
 223 | var layout = {
 224 |         title: {text: "Profit and loss statement 2018"},
 225 |         xaxis: {type: "category"},
 226 |         yaxis: {type: "linear"},
 227 |         autosize: true,
 228 |         showlegend: true
 229 |     };
 230 | 
 231 | window.renderPlotly(this.container, data, layout)
 232 | 
 233 | ```
 234 | 
 235 | # Funnel Plot
 236 | Found [here](https://plotly.com/javascript/funnel-charts/#basic-funnel-plot).
 237 | This example contains `var gd = document.getElementById('myDiv');` something which we simply do not need as the graph is being rendered by `this.container`
 238 | 
 239 | ```dataviewjs
 240 | 
 241 | let path = app.vault.adapter.basePath;
 242 | var d3 = require(path+"//d3.v7.min.js");
 243 | console.log(d3)
 244 | 
 245 | var data = [{type: 'funnel', y: ["Website visit", "Downloads", "Potential customers", "Invoice sent", "Closed delas"], x: [13873, 10533, 5443, 2703, 908], hoverinfo: 'x+percent previous+percent initial'}];
 246 | 
 247 | var layout = {margin: {l: 150}, width:600, height: 500}
 248 | 
 249 | window.renderPlotly(this.container, data, layout)
 250 | 
 251 | ```
 252 | 
 253 | In essence the [Plotly.js website](https://plotly.com/javascript/) examples just need to be pre-pended with:
 254 | ```
 255 | // If not using yaml values
 256 | let path = app.vault.adapter.basePath;
 257 | var d3 = require(path+"//d3.v7.min.js");
 258 | ```
 259 | or
 260 | ```
 261 | // If using yaml values
 262 | let pg = dv.current()
 263 | let path = app.vault.adapter.basePath;
 264 | var d3 = require(path+"//d3.v7.min.js");
 265 | ```
 266 | 
 267 | And then `Plotly.newPlot(div, data, layout)` replaced with `window.renderPlotly(this.container, data, layout)`.
 268 | 
```

---
## manifest.json

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\manifest.json`
- **Tamanho:** 309 bytes
- **Linhas:** 11
- **Caracteres:** 299
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```json
   1 | {
   2 | 	"id": "obsidian-plotly",
   3 | 	"name": "Plotly",
   4 | 	"version": "0.0.6",
   5 | 	"minAppVersion": "0.9.12",
   6 | 	"description": "Obsidian plugin, which allow user to embed Plotly charts into markdown notes.",
   7 | 	"author": "Dmitriy Shulha",
   8 | 	"authorUrl": "https://github.com/Dmitriy-Shulha",
   9 | 	"isDesktopOnly": false
  10 | }
  11 | 
```

---
## package.json

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\package.json`
- **Tamanho:** 892 bytes
- **Linhas:** 31
- **Caracteres:** 892
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```json
   1 | {
   2 |   "name": "obsidian-plotly",
   3 |   "version": "0.0.6",
   4 |   "description": "Obsidian plugin, which allow user to embed Plotly charts into markdown notes.",
   5 |   "main": "src/main.js",
   6 |   "scripts": {
   7 |     "dev": "rollup --config rollup.config.js -w",
   8 |     "build": "rollup --config rollup.config.js --environment BUILD:production"
   9 |   },
  10 |   "keywords": [],
  11 |   "author": "Dmitriy Shulha",
  12 |   "license": "MIT",
  13 |   "devDependencies": {
  14 |     "@rollup/plugin-commonjs": "^18.0.0",
  15 |     "@rollup/plugin-node-resolve": "^11.2.1",
  16 |     "@rollup/plugin-typescript": "^8.2.1",
  17 |     "@types/node": "^14.14.37",
  18 |     "@types/plotly.js-dist-min": "^2.3.0",
  19 |     "codemirror": "^5.62.3",
  20 |     "obsidian": "^0.12.0",
  21 |     "rollup": "^2.32.1",
  22 |     "rollup-plugin-svgo": "^1.1.0",
  23 |     "tslib": "^2.2.0",
  24 |     "typescript": "^4.2.4"
  25 |   },
  26 |   "dependencies": {
  27 |     "@rollup/plugin-json": "^4.1.0",
  28 |     "plotly.js-dist-min": "^2.5.0"
  29 |   }
  30 | }
  31 | 
```

---
## rollup.config.js

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\rollup.config.js`
- **Tamanho:** 794 bytes
- **Linhas:** 34
- **Caracteres:** 761
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```javascript
   1 | import typescript from '@rollup/plugin-typescript';
   2 | import {nodeResolve} from '@rollup/plugin-node-resolve';
   3 | import commonjs from '@rollup/plugin-commonjs';
   4 | import svgo from 'rollup-plugin-svgo';
   5 | import json from '@rollup/plugin-json';
   6 | 
   7 | const isProd = (process.env.BUILD === 'production');
   8 | 
   9 | const banner = 
  10 | `/*
  11 | THIS IS A GENERATED/BUNDLED FILE BY ROLLUP
  12 | if you want to view the source visit the plugins github repository
  13 | */
  14 | `;
  15 | 
  16 | export default {
  17 |   input: 'src/main.ts',
  18 |   output: {
  19 |     dir: './build/',
  20 |     sourcemap: 'inline',
  21 |     sourcemapExcludeSources: isProd,
  22 |     format: 'cjs',
  23 |     exports: 'default',
  24 |     banner,
  25 |   },
  26 |   external: ['obsidian'],
  27 |   plugins: [
  28 |     typescript(),
  29 |     nodeResolve({browser: true}),
  30 |     commonjs(),
  31 |     svgo(),
  32 |     json(),
  33 |   ]
  34 | };
```

---
## main.ts

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\src\main.ts`
- **Tamanho:** 2.3 KB
- **Linhas:** 79
- **Caracteres:** 2282
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```typescript
   1 | import * as Plotly from 'plotly.js-dist-min';
   2 | 
   3 | import { Editor, MarkdownView, Plugin } from 'obsidian';
   4 | import { preprocessor, renderPlotly } from './preprocessor';
   5 | 
   6 | const basicPlotlyChart = [
   7 | 	'```plotly',
   8 | 	'data:',
   9 | 	'- x: [0,1,2]',
  10 | 	'  y: [0,1,0]',
  11 | 	'```\n'
  12 | ].join('\n')
  13 | const NEW_PLOTLY_CHART_NAME = "New Plotly Chart";
  14 | const newPlotlyChart = (editor: Editor)=>{
  15 | 	let doc = editor.getDoc();
  16 | 	let cursor = doc.getCursor();
  17 | 	doc.replaceRange(basicPlotlyChart, cursor);
  18 | }
  19 | 
  20 | const dataviewjsPlotlyChart = [
  21 | 	'```dataviewjs',
  22 | 	'//Some plotly examples require d3 library to work.',
  23 | 	'//Since it\'s large and used by few examples,',
  24 | 	'//I propose a workaround to import d3;',
  25 | 	'//You need to download dependency from https://d3js.org/d3.v7.min.js',
  26 | 	'//and place it in your vault.',
  27 | 	'let path = app.vault.adapter.basePath;//absolute path to your vault',
  28 | 	'var d3 = require(path+"\\\\utils\\\\d3.v7.min.js");',
  29 | 	'',
  30 | 	'//Replace this block with any example from plotly.com',
  31 | 	'//NOTE: `Plotly.newPlot` won\'t work here, use `window.renderPlotly` instead',
  32 | 	'var data = [',
  33 | 	'{x:[0,1,2,3,4,5,6,7,8,9],y:[4,4,2,2,3,3,2,2,4,4]},',
  34 | 	'{x:[0,1,2,3,4,5,6,7,8,9],y:[3,3,1,1,2,2,1,1,3,3]}',
  35 | 	'];',
  36 | 	'var layout = {};',
  37 | 	'var config = {};',
  38 | 	'',
  39 | 	'window.renderPlotly(this.container, data, layout, config)',
  40 | 	'```'
  41 | ].join('\n')
  42 | const NEW_PLOTLY_CHART_BY_DATAVIEWJS_NAME = "New Plotly Chart generated by Dataviewjs";
  43 | const newPlotlyChartByDataviewjs = (editor: Editor)=>{
  44 | 	let doc = editor.getDoc();
  45 | 	let cursor = doc.getCursor();
  46 | 	doc.replaceRange(dataviewjsPlotlyChart, cursor);
  47 | }
  48 | 
  49 | 
  50 | export default class PlotlyPlugin extends Plugin {
  51 | 	Plotly: object
  52 | 
  53 | 	async onload() {
  54 | 		//@ts-ignore
  55 | 		window.renderPlotly = renderPlotly;
  56 | 		
  57 | 		console.log('loading Plotly plugin');
  58 | 		this.Plotly = Plotly;
  59 | 		
  60 | 		this.registerMarkdownCodeBlockProcessor('plotly', preprocessor);
  61 | 
  62 | 		this.addCommand({
  63 | 			id: "add-plotly-example",
  64 | 			name: NEW_PLOTLY_CHART_NAME,
  65 | 			editorCallback: (editor: Editor, view: MarkdownView)=>newPlotlyChart(editor)
  66 | 		});
  67 | 
  68 | 		this.addCommand({
  69 | 			id: "add-plotly-dataviewjs-example",
  70 | 			name: NEW_PLOTLY_CHART_BY_DATAVIEWJS_NAME,
  71 | 			editorCallback: (editor: Editor, view: MarkdownView)=>newPlotlyChartByDataviewjs(editor)
  72 | 		});
  73 | 	}
  74 | 
  75 | 	onunload() {
  76 | 		console.log('unloading Plotly plugin');
  77 | 	}
  78 | }
  79 | 
```

---
## preprocessor.ts

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\src\preprocessor.ts`
- **Tamanho:** 1.4 KB
- **Linhas:** 47
- **Caracteres:** 1426
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```typescript
   1 | import * as Plotly from 'plotly.js-dist-min';
   2 | 
   3 | import { MarkdownPostProcessorContext, parseYaml } from "obsidian";
   4 | 
   5 | export const preprocessor = (content: string, el: HTMLElement, ctx: MarkdownPostProcessorContext)=>{
   6 |     let json;
   7 |     try{
   8 |         json = parseYaml(content);
   9 |         validate(json, el)
  10 |         render(json, el)
  11 |     } catch (error) {
  12 |         let errorDiv = document.createElement('div');
  13 |         errorDiv.textContent = "Couldn't render plot:" + error;
  14 |         el.appendChild(errorDiv);
  15 |     }
  16 | }
  17 | 
  18 | const allowValues = ["data", "layout", "config"];
  19 | 
  20 | const validate = (json: any, el: HTMLElement) => {
  21 |     if(!json){
  22 |         throw "There should be a valid JSON in this block."
  23 |     }
  24 | 
  25 |     Object.keys(json).forEach(key=>{
  26 |         if(!allowValues.contains(key)){
  27 |             throw "The only valid keys are data, layout and config."
  28 |         }
  29 |     })
  30 | }
  31 | 
  32 | const render = (json: any, el: HTMLElement) => {
  33 |     renderPlotly(el, json.data, json.layout, json.config)
  34 | }
  35 | 
  36 | export const renderPlotly = (el: HTMLElement, data: Object[], layout: Object, config: Object) => {
  37 |     const destination = document.createElement('div');
  38 | 
  39 |     if(el.firstElementChild!=null){
  40 |         Plotly.update(destination, data as any, layout, config as any);        
  41 |         el.replaceChild(destination, el.firstElementChild);
  42 |     } else {
  43 |         Plotly.newPlot(destination, data, layout, config);        
  44 |         el.appendChild(destination);
  45 |     }
  46 | }
  47 | 
```

---
## styles.css

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\styles.css`
- **Tamanho:** 0 bytes
- **Linhas:** 1
- **Caracteres:** 0
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```css
   1 | 
```

---
## tsconfig.json

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\tsconfig.json`
- **Tamanho:** 400 bytes
- **Linhas:** 23
- **Caracteres:** 378
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```json
   1 | {
   2 |   "compilerOptions": {
   3 |     "baseUrl": "./src/",
   4 |     "inlineSourceMap": true,
   5 |     "inlineSources": true,
   6 |     "module": "ESNext",
   7 |     "target": "es6",
   8 |     "allowJs": true,
   9 |     "noImplicitAny": true,
  10 |     "moduleResolution": "node",
  11 |     "importHelpers": true,
  12 |     "lib": [
  13 |       "dom",
  14 |       "es5",
  15 |       "scripthost",
  16 |       "es2015"
  17 |     ]
  18 |   },
  19 |   "include": [
  20 |     "**/*.ts"
  21 |   ]
  22 | }
  23 | 
```

---
## versions.json

**Informações do Arquivo:**
- **Caminho:** `D:\Downloads\obsidian-plotly-master\versions.json`
- **Tamanho:** 131 bytes
- **Linhas:** 9
- **Caracteres:** 123
- **Encoding:** utf-8
- **Modificado:** 2025-11-16 23:01:02

**Conteúdo:**

```json
   1 | {
   2 | 	"0.0.6": "0.9.12",
   3 | 	"0.0.5": "0.9.12",
   4 | 	"0.0.4": "0.9.12",
   5 | 	"0.0.3": "0.9.12",
   6 | 	"0.0.2": "0.9.12",
   7 | 	"0.0.1": "0.9.12"
   8 | }
   9 | 
```
