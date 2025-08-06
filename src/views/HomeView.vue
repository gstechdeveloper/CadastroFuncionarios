<template>
  <div class="container p-5">
    <form-component></form-component>
    <list-component></list-component>
  </div>
</template>

<style>
  body{
    background: #111 !important;
  }
</style>

<style scoped>

</style>

<script>
import FormComponent from '@/components/FormComponent.vue';
import ListComponent from '@/components/ListComponent.vue';

export default {
  name: 'HomeView',
  components: {
    FormComponent,
    ListComponent
  }
}

</script>
