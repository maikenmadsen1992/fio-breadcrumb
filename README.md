# fio-breadcrumb

## Install
```
npm install fio-breadcrumb
```

## Usage
In the component where you want to use it:
```
import fiobreadcrumb from "fio-breadcrumb";
```
If you want to use the css provided you have to add the following under the import:
```
import 'fio-breadcrumb/dist/fio-breadcrumb.css';
```

### Props/attributes
```
<breadcrumb :items="dataitems" :icon="icon" v-on:breadcrumbItemClicked="itemIsClicked"/>
```

1. icon is the icon between the text. There is two types of icons arrow-right and chevron-right parse it as a string
2. breadcrumbItemClicked is the function where the user have pressed a breadcrumb item
3. items is an array of objects looking like:

```
{'text': 'Category1', 'value': 'if you want to parse some more information'},
{'text': 'Category2', 'value': 'if you want to parse some more information'},
{'text': 'Category3', 'value': 'if you want to parse some more information'},
{'text': 'Category4', 'value': 'if you want to parse some more information'}
```

## Example

In the github project src/App.vue a simple example is presented.

### Youtube

Here is a short link with a simple presentation: https://youtu.be/rnaxOiDwGKI


## Github

Link: https://github.com/maikenmadsen1992/fio-breadcrumb