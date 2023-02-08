<template>
    <h1>Enviando dados para component filho</h1>
    <div :class="baseClass">
        <slot />
        <button @click="onClick">X</button>
    </div>
</template>
<script>
export default {
    props: {
        variant: {
            type: String,
            default: '',
        },
    },
    computed: {
        baseClass() {
            return ['alert', this.variant ? `alert-${this.variant}` : ''];
        },
    },
    methods: {
        onClick() {
            console.log('clicou');
            this.$emit('close');
        },
    },
};
</script>
<style scoped>
.alert {
    display: flex;
    justify-content: space-between;
    padding: 5px;
    border-radius: 6px;
    color: gray;
    background: rgb(99, 86, 86);
}
.alert-sucess {
    padding: 5px;
    border-radius: 6px;
    color: #fffcfc;
    background: green;
}
.alert-danger {
    padding: 5px;
    border-radius: 6px;
    color: #fffcfc;
    background: red;
}
</style>
