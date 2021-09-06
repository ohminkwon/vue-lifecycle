<template>
  <section v-if="hasFruit">
    <h1>Fruits</h1>
    <ul>
      <li
        v-for="fruit in fruits"
        :key="fruit">
        {{ fruit }}
      </li>
    </ul>
  </section>
  <section>
    <h1>Reverse Fruits</h1>
    <ul>
      <li
        v-for="fruit in reverseFruit"
        :key="fruit">
        {{ fruit }}
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return{
      fruits: [
        'Apple', 'Banana', 'Cherry'
      ]
    }
  },
  computed:{
    hasFruit(){
      return this.fruits.length > 0
    },
    reverseFruit(){
      return this.fruits.map(fruit=>{
        // 'Apple' => ['A', 'p', 'p', 'l', 'e'] => ['e', 'l', 'p', 'p', 'A']
        return fruit.split('').reverse().join('')
      })
    }
  }
}
</script>