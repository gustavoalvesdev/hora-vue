<template>
    <div>
        <button @click="primeiro($event), segundo($event)">Ativar múltiplos eventos</button>
        <p>{{ multiplos_eventos }}</p>
    </div>    
</template>
<script>
export default {
    name: 'MultiplosEventos',
    data() {
        return {
            multiplos_eventos: ""
        }
    },
    methods: {
        primeiro(e) {
            e.preventDefault();
            this.multiplos_eventos = "Primeiro evento ativado";
        },
        segundo(e) {
            e.preventDefault();

            setTimeout(() => {
                this.multiplos_eventos = "Segundo evento!"
            }, 500)
        }
    }
}   
</script>
<style scoped>
    div {
        margin: 100px;
    }
</style>