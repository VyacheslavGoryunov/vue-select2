# Vue Select2 Component

This project was generated with [Vue cli](https://github.com/vuejs/vue-cli) version 2.9.1.

## Instructions
This project is built for showing how to use v-select2-component.

**If you want to use it in Vue 3.0, check [vue3-select2-component](https://github.com/godbasin/vue-select2/tree/npm-publish-code-for-vue3).**

# v-select2-component

Source code in: [https://github.com/godbasin/vue-select2/tree/npm-publish-code](https://github.com/godbasin/vue-select2/tree/npm-publish-code).

## Related Versions

Vue-Select2-Component is baseed on these plugins and libs(version):
- [vue(>= 2.0-release)](https://github.com/vuejs/vue)
- [jQuery](https://jquery.com/)
- [select2](https://select2.github.io/)

## How to use 
---
### Install
``` cmd
// npm install
npm install v-select2-component --save
```

### Use as component
1. import as global component.
``` javascript
// import Select2Component
import Select2 from 'v-select2-component';

Vue.component('Select2', Select2);
new Vue({
	// ...
})
```

2. import into a single component.
``` javascript
// import Select2Component
import Select2 from 'v-select2-component';

<template>
  <div>
    <Select2 v-model="myValue" :options="myOptions" :settings="{ settingOption: value, settingOption: value }" @change="myChangeEvent($event)" @select="mySelectEvent($event)" />
    <h4>Value: {{ myValue }}</h4>
  </div>
</template>
<script>
export default {
    // declare Select2Component
    components: {Select2},
    data() {
        return {
            myValue: '',
            myOptions: ['op1', 'op2', 'op3'] // or [{id: key, text: value}, {id: key, text: value}]
        }
    },
    methods: {
        myChangeEvent(val){
            console.log(val);
        },
        mySelectEvent({id, text}){
            console.log({id, text})
        }
    }
}
</script>
```

### Options
- `options`: `option[]`
  - select options for select2
  - `option`: `{id: key, text: value}` or `string`
- `v-model`: option value that is selected
  - `id` or `string` while multiple is disable
  - `id[]` or `string[]` while multiple is enable
- `disabled`
  - if select is disabled
- `settings`
  - configurable settings, see [Select2 options API](https://select2.org/configuration/options-api)
  - `setting`: `{ settingOption: value, settingOption: value }`

### Events
- `change`
  - triggered when option selected change
  - return value
  - parmas: same with `v-model`
- `select`
  - triggered when option selected
  - parmas: `option`(`{id: value, text: key, selected: ifSelected}` or `string`)
- `open`
  - triggered whenever the dropdown is opened
- `close`
  - triggered whenever the dropdown is closed
- `clear`
  - triggered whenever the dropdown is cleared
- more events refer to [select2 events](https://select2.org/programmatic-control/events)