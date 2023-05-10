# Why Vue js?

Vue is a JavaScript framework for building user interfaces.provides a declarative and component-based programming model that helps you efficiently develop user interfaces, be they simple or complex.

# Single File Component

Vue codes are written is a special fashion where HTML will go inside `<template/>` tag and Css will go inside `<style/>` tag and all js will go inside `<script/>` tag.

Basically SFC is a design pattern which encapsulates the the code of a component in a greater manner and vue is following SFC.

# API Styles

Vue component can be styled in two ways

1. Option API
2. Composition API

# Option API

In Option API we have to define product logics using an object of options such as data, computed, mounted, methods etc...

Option API is beginner friendly and It is better to use Option API if you want to understand the Vue component Lifecycle in an easy way.

Example:
```html
<script>
export default{
// Properties returned from data() become reactive state and will be exposed on `this`.
    data(){
        return {
            count:0
        }
    },
// Methods are functions that mutate state and trigger updates.They can be bound as event listeners in templates.
    methods:{
        increment(){
            this.count++;
        }
        decrement(){
            this.count--;
        }
    },
// Lifecycle hooks are called at different stages of a component's lifecycle. This function will be called when the component is mounted.
    mounted(){
        console.log("initial State of count : "+this.count);
    }
}
</script>
<template>
    <h1>Count: {{count}}</h1>
    <button v-on:click="decrement">-</button>
    <button v-on:click="increment">+</button>
</template>
```

# Composition API
In Composition API we define a component logic using imported API Function. In SFC Composition API is typically used inside `<script setup/>` where setup key used during compilation when compiler will convert this to Option API and then compile accordingly.

Example:

```html
<script setup>
    import {ref,onMounted} from "vue";
    const count = ref(0);
    increment(){
        count.value= count.value+1;
    }
    decrement(){
        count.value = count.value-1;
    }

    onMounted(()=>{
        console.log("initial State of count : "+count.value);
    })
</script>
<template>
    <h1>Count: {{count}}</h1>
    <button v-on:click="decrement">-</button>
    <button v-on:click="increment">+</button>
</template>
```
