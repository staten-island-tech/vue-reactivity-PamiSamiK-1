<template>
  <div>

  </div>
</template>
 

<script>
  export default {
    const houses=[
      {adress:"67 Nicole Loop, Staten Island, NY 10301",
      price:" $1,286,800",
      bedrooms:"4",
      bath:"4",
      sqft:"4,400 sqft",
   }

   {
    adress:"7025 W 63rd St, Chicago, IL 60638",
    price:"$419,000",
    bedrooms:"4",
    bath:"3",
    sqft:"1,250 sqft"}

    {adress:""}
    ]
  }
</script>

<style lang="scss" scoped>

</style>


// store.js
import { reactive } from 'vue'

export const store = reactive({
  count: 0
})
<!-- ComponentA.vue -->
<script setup>
import { store } from './store.js'
</script>

<template>From A: {{ store.count }}</template>

<!-- ComponentB.vue -->
<script setup>
import { store } from './store.js'
</script>

<template>From B: {{ store.count }}</template>

<template>
  <button @click="store.count++">
    From B: {{ store.count }}
  </button>
</template>
