# migrate-cra-to-vite
A tutorial migration from CRA to Vite in React

The approach of "Create React App" or in short "CRA" is one of the common approaches to creating a web application by React which under the hood of "Webpack" has a unity structure and ease of development.
One of the advantages of "Vite" is uses "module" rather than "bundle" which is caused in the case of updating a project without spending time only building the specific module.

Whatever is not complete or doesn't have any problems and there is an opening opportunity to improve but it could be taken into account is the best choice to improve the speed of development.

In this post, the stages of migration are provided sequentially.

1- Install the following packages.

yarn add @typescript-eslint/eslint-plugin @typescript-eslint/parser @vitejs/plugin-react eslint eslint-plugin-react-hooks eslint-plugin-react- refresh typescript vite -d



2- The following files add to the root of the project

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/tsconfig.json

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/tsconfig.node.json

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/vite.config.ts

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/.eslintrc.cjs



3- The "index.html" file needs to move from the public folder to the root

Because the automatic address is generated in public there is no need to have %PUBLIC_URL% and it needs to be removed.



The start point of the program for example "index.js" should be inserted inside the body of the HTML page

```html
 <script type="module" src="/src/index.tsx"></script>
 ```


4- Remove react-scripts packages

```shell
npm uninstall react-scripts
```


5- The content of Scripts in package.json needs to be changed as a bellowing demo

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/package.json



6- How to access the environment by changing the variable from process to import.meta

previous
```js
process.env.REACT_APP_VARIABLE
```

new import
```js
import.meta.env.REACT_APP_VARIABLE
```

A benefit of Vite is reloading the app after the environment changes

7- the file of  vite-env.d.ts into src should be placed

https://github.com/muhamadzolfaghari/migrate-cra-to-vite/blob/master/src/vite-env.d.ts





 
