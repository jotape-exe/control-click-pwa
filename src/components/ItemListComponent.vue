<script setup lang="ts">

const props = defineProps(['username','secondName', 'phone', 'mail'])

</script>

<template>
  <div class="card">
      <h3>{{ props.username }}</h3>
      <ul class="list-card">
            <li class="list-item">{{ props.secondName }}</li>
            <li class="list-item">{{ props.phone }}</li>
            <li class="list-item">{{ props.mail }}</li>
      </ul>
      <div style="display: flex; flex-direction: row; flex-shrink: 0; align-self: flex-end;">
          <button class="btn-1">Editar</button>
          <button class="btn-2">Exportar</button>
     </div>
  </div>
</template>

<style>
 .card{
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      border-radius: 10px;
      background-color: rgb(68, 102, 255);
      padding: .8rem;
      margin: 5px;
 }
 .list-card{
      list-style: none;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
 }
 .list-item{
     margin: 0 0 5px 0;
 }
 button{
     border: none;
     border-radius: 4px;
     padding: .4rem;
     font-size: 20px;
     width: 100px;
 }
 .btn-1{
     background-color: #fff;
     color: #1e31da;
     cursor: pointer;
     margin: 0 7px 0 0;
 }

 .btn-2{
     color: #fff;
     background-color: #1e31da;
     cursor: pointer;
 }
</style>