<template>
    <h1>Observadores - watch</h1>
    <div>
       <input type="text" v-model="name"> 
       <br>
       {{ name }}
    </div>
</template>

<script>
export default {
    name: 'TheObservador',
    data() {
        return {
            name:''
        };
    },
    watch:{
        name(vl){
            if(vl.length >= 6){
                this.saveUserName()
            }
        }
    },
    computed:{

    },
    methods:{
        saveUserName(){
            console.log(`Me chamou: ${this.name}`);
        }
    }
};
</script>

<style></style>
