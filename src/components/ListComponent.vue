<template>
    <div class="row mt-5">
        <div class="col title">
            Nome
        </div>
        <div class="col title">
            Email
        </div>
        <div class="col title">
            Data de Nascimento
        </div>
        <div class="col title">
            Sexo
        </div>
        <div class="col title">
            Deficiência
        </div>
    </div>
    <div class="row" v-for="(item, index) in listar" :key="index">
        <div class="col item">
            {{ item['nome'] }}
        </div>
        <div class="col item">
            {{ item['email'] }}
        </div>
        <div class="col item">
            {{ item['datanascimento'] }}
        </div>
        <div class="col item">
            {{ item['sexo'] }}
        </div>
        <div class="col item">
            {{ item['deficiencia'] }}
        </div>
    </div>
</template>

<style scoped>
    .title{
        background: darkgreen;
        text-align: center;
        color: white;
        padding: 5px
    }
    .item{
        background: #181818;
        color: white;
        text-align: center;
        padding: 10px;
    }
</style>

<script setup>
    import { useStore } from "vuex"
    import { computed } from "vue"

    const store= useStore()
    
    const listar= computed(() => store.state.registros)
</script>