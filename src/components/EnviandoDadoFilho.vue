<template>
    <h1>Enviando dados para component filho</h1>
    <div :class="baseClass">
        {{ test }}
        <slot></slot>
    </div>
</template>
<script>
export default {
    props: {
        variant: {
            type: String,
            default: '',
        },
        test: {
            type: String,
            default: 'test',
        },
    },
    computed: {
        baseClass() {
            return ['alert', this.variant ? `alert-${this.variant}` : ''];
        },
    },
};
</script>
<style scoped>
.alert {
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
