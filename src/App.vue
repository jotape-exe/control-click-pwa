<script setup lang="ts">
import { computed, onMounted, ref } from 'vue'
import ItemListComponent from './components/ItemListComponent.vue';

const hello = ref('Hello VITE')
const idade = ref(17)
const userDbFake = [
  {
    name: 'John',
    secondName: 'Doe',
    phone: '+123 432 432',
    mail: 'johndoe@email.com'
  },
  {
    name: 'Alice',
    secondName: 'Johnson',
    phone: '+456 789 123',
    mail: 'alice@email.com'
  },
  {
    name: 'Bob',
    secondName: 'Smith',
    phone: '+789 321 654',
    mail: 'bobsmith@email.com'
  },
  {
    name: 'Eva',
    secondName: 'Brown',
    phone: '+987 654 321',
    mail: 'eva@email.com'
  }
];


onMounted(()=>{
  hello.value = "Hello Vite & Vue"
})

const getMaiorDeIdade = computed(()=> {
  return idade.value < 18 ? "Menor de Idade" : "Maior de Idade"
})
</script>

<template>
  <div style="width: 100%; display: flex; align-items: center; justify-content: center; padding: 1rem;">
    <div style="padding: 1rem; flex-wrap: wrap; max-width: 80vw; border-radius: 10px; background-color: #7484e0; display: flex; flex-direction: row; align-items: center; justify-content: center;">
      <h1 style="width: 100%; text-align: center; margin-bottom: 10px;">{{ hello }}</h1>
      <br />
      <ItemListComponent v-for="item in userDbFake"
      :key="item"
      :second-name="item.secondName"
      :username="item.name"
      :phone="item.phone"
      :mail="item.mail"/>
    </div>
  </div>
</template>

<style scoped>
.separator{
  height: 1px;
  width: 50%;
  margin-top: 10px;
  background-color: #ffffff;
}
</style>
