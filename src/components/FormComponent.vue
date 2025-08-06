<template>
    <div class="row justify-content-center">
      <div class="col-6 formulario">
        <h1>Cadastro de Funcionarios</h1>
        
        <div class="container">
            <div class="row">
                <input type="text" v-model="nome" placeholder="Nome do Funcionário">
            </div>
            <div class="row">
                <input type="email" v-model="email" placeholder="E-mail do Funcionário">
            </div>
            <div class="row">
                <input type="date" v-model="datanascimento">
            </div>
            <div class="row">
                <select v-model="sexo">
                    <option>Selecione seu sexo</option>
                    <option value="M">Masculino</option>
                    <option value="F">Feminino</option>
                    <option value="D">Prefiro não dizer</option>
                </select>
            </div>

            <div class="row mt-2">
                <div>
                    <input type="checkbox" v-model="deficiencia">
                    Portador de deficiência
                </div>
            </div>

            <div class="row">
                <button class="btn btn-success mt-3" @click="registrar">Cadastrar</button>
            </div>
        </div>
      </div>
    </div>
</template>

<style scoped>
    .formulario{
        color: white;
        border: 1px solid #333;
        border-radius: 10px;
        padding: 30px;
        text-align: center;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    input, select{
        text-align: center;
        background: transparent;
        border: 1px solid #333;
        border-radius: 5px;
        padding: 10px;
        font-size: 1.2rem;
        color: white;
        margin-top: 10px;
    }

    select > option{
        background: #111
    }
</style>

<script setup>
    import { useStore } from "vuex"
    import { ref } from "vue"

    const store= useStore()

    const nome= ref("")
    const email= ref("")
    const datanascimento= ref("")
    const sexo= ref("")
    const deficiencia= ref("")

    
    const registrar= () => {store.state.registros.push(
        {
            nome: nome.value,
            email: email.value,
            datanascimento: datanascimento.value,
            sexo: sexo.value,
            deficiencia: deficiencia.value ? "Sim" : "Não"
        }
    )
    }
</script>