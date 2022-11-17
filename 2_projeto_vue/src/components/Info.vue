<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades</p>
        <p>Utilizo as seguintes tecnologias:</p>
        <ul>
            <li>JavaScript</li>
            <li>PHP</li>
            <li>Python</li>
        </ul>
        <div>
            <button @click="showEmail">{{ texto_botao }}</button>
        </div>
        <p v-show="mostrar_email">Mande mensagem para: {{ email }}</p>
        <p class="teste">Para acessar meu portfólio basta clicar <a v-bind:href="meu_link" target="_blank">aqui</a></p>
        <Picture />
    </div>
</template>
<script>

    import Picture from './Picture.vue';

    export default {
        name: 'Info',
        components: {
            Picture
        },
        data() {
            return {
                esta_trabalhando: false,
                mostrar_email: false,
                email: 'gustavoalvesdasilva@outlook.com',
                meu_link: 'https://gustavoalvesdev.com.br',
                texto_botao: 'Mostrar e-mail'
            }
        },
        methods: {
            showEmail() {
                this.mostrar_email = !this.mostrar_email
                if (!this.mostrar_email) {
                    this.texto_botao = "Mostrar e-mail"
                } else {
                    this.texto_botao = "Esconder e-mail"
                }
            }
        }
    }
</script>

<style>
    .paragrafo-pai {
        color: red;
    }
</style>