<script setup>
    const nome = 'Luana'
    const idade = 16

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

    import { ref, onMounted } from 'vue'

    const contador = ref(0)

    function incrementarContador() {
        contador.value++
    }

    function decrementarContador() {
        if(contador.value > 0) {
        contador.value--;
    }
    }

    function zerarContador() {
        contador.value = 0;
    }   

    onMounted(() => {
        console.log(`O valor inicial do contador é ${contador.value}.`)
    })

</script>

<template id="container">
    <div>
        <h1 style="margin-left: 20%;">{{ contador }}</h1>
        <button @click="incrementarContador">Incrementar</button>
         <button @click="decrementarContador">Decrementar</button>
         <button @click="zerarContador">Zerar</button>
         <div style="width: 150px; margin-top: 5px;">
            <h2 v-if="contador > 10" style="background-color: green;">Maior que 10</h2>
            <h2 v-else="contador < 10" style="background-color: red;">Menor que 10</h2>
         </div>
         
    </div>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
</template>

<style scoped>
.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: rgb(255, 255, 255);
  font-weight: bold;
  font-size: 1.5em;
}

</style>

