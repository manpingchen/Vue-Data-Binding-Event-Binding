# Vue Data Binding and Event Binding
 
### Click event: v-on:click
```html
<button v-on:click="add(10)" class="mr-1">Add 10</button>
```

### Two way binding: v-model
1. Set the data needed in the data function
```js
data() {
    return {
      counter: 0,
      name: "",
    };
  },
 ```
2. Bind the returned object value with html
```html
 <input type="text" v-model="name" />
```

### Computed Caching
>computed properties are cached based on their reactive dependencies. A computed property will only re-evaluate when some of its reactive dependencies have changed. 
```js
computed: {
    fullname() {
      console.log("running again...");
      if (this.name === "") {
        return "";
      }
      return this.name + " " + "Chen";
    },
  },
```
fullname() will only be re-render when its reactive dependencies have changed.
```html
<p class="background">{{ fullname }}</p>
```

### Form submit prevent default refreshing
with ```v-on:submit.prevent="submit"``` the submit event default will be prevented
```html
<form v-on:submit.prevent="submit">
 <label htmlFor="name">Name</label>
 <input type="text" v-model="name" id="name" />
 <button class="w-100">Sign Up</button>
</form>
```
