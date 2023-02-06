<template>
    <div>
        <h1>Life Cycle - ciclo de vida</h1>
        <h4>Hello WOld</h4>
        {{ name }}
    </div>
</template>

<script>
export default {
    name: 'TheLiveCycle',
    data() {
        return {
            name: 'Edmar',
        };
    },
    // Criação
    // preparar o componente
    // ajax, inicializa algumas variáveis
    // Não tem acesso ao template (DOM)

    // Montagem
    // INicializa uma lib externa (new Lib())
    // Precisa de acesso ao template (DOM)
    // Tem acesso ao template(dom)
    // Atualização
    // Debug
    // Update
    // Desmontagem
    // Remover tudo o que for necessário (lib->destroy())
    // Para liberar memória

    // Hooks
    beforeCreate() {
        console.log('beforeCreate');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    created() {
        console.log('created');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    beforeMount() {
        console.log('beforeMount');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    mounted() {
        console.log('mounted');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    beforeUnmount() {
        console.log('beforeUnmount');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    unmounted() {
        console.log('unmounted');
        console.log('Estado: ', this.name);
        console.log('DOM: ', this.$el);
    },
    watch: {},
    computed: {},
    methods: {},
};
</script>

<style></style>
