<template>
    <!-- <header class="header">{{ h1 }}</header> -->
    <h1 :class="{ title: true, 'title-home': isHome }">Curso VUE 3</h1>
    <p :class="[pclass]">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem, facilis ducimus sapiente iusto sunt est assumenda veniam repellat natus
        quaerat velit sequi ex? Quasi repellat officia aliquam ut quaerat soluta, fugiat assumenda optio officiis exercitationem quod accusantium
        perspiciatis recusandae harum quidem obcaecati reiciendis. Ea sapiente in, debitis dicta eos nihil.
    </p>
    <p :style="styleClass">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dicta vel facere officia et, inventore iusto dignissimos? Laboriosam animi repellat
        soluta!
    </p>
    <div v-for="obj in todos" :key="obj.id" class="todos-itens">
        <p>{{ obj.title }}</p>
        <img :src="obj.imgSrc" v-if="obj.imgSrc" v-bind:alt="obj.imgAlt" />
    </div>

    <div>
        <div>
            one-way data binding <br />
            Two-way data binding <br />
            v-model -> formulários
            <br />
            <br />
            <label>Nome</label>
            <input type="text" v-model="name" /><br />
            {{ name }}

            <br /><br />
            <select v-model="sports">
                <option value="">Escolha</option>
                <option value="futebol">Futebol</option>
                <option value="skate">Skate</option>
                <option value="Tenis">Tenis</option>
            </select>
            <br /><br />
            {{ sports }}
            <br /><br />
            <div>
                <label for="">Newsletter</label>
                <input type="radio" v-model="newsletter" value="sim" />sim <input type="radio" v-model="newsletter" value="nao" />não <br /><br />
                {{ newsletter }}
            </div>
            <br /><br />
            <div>
                <label for="">Contrato</label> <br />
                <input type="checkbox" v-model="contract" /> aceita nosso contrato..<br />
                {{ contract }}
                <br />
            </div>

            <br />
            <div>
                <label for="">Cores que você mais gosta</label> <br />
                <input type="checkbox" v-model="colors" value="amarelo" /> amarelo <input type="checkbox" v-model="colors" value="azul" /> azul<br />
                {{ colors }}
                <br />
            </div>
        </div>
        <br />
        <br />
        <div>
            <button @:click="onClick">Enviar</button>
        </div>
        <div @mouseover="onMouseOver" @mouseout="onMouseOut">Mouser over</div>
        <br />
        <br />
        <form action="https://google.com" v-on:submit.prevent="onSubmit">
            <input type="text" @keyup.enter="onKeyUp" />
            <button type="submit">Enviar</button>
        </form>
    </div>
    <TheComputada />
    <TheObeservador />
    <TheLifeCycle />
    <BaseCard />
    <EnviandoDadoFilho :variant="variant">
        {{ text }}
    </EnviandoDadoFilho>
</template>

<script>
import TheComputada from '@/components/TheComputada.vue';
import TheObeservador from '@/components/TheObservador.vue';
import TheLifeCycle from './TheLifeCycle.vue';
import BaseCard from './BaseCard.vue';
import EnviandoDadoFilho from './EnviandoDadoFilho.vue';
export default {
    name: 'TheHeader',
    data() {
        return {
            h1: 'Olá, VUE!',
            todos: [
                {
                    userId: 1,
                    id: 1,
                    title: 'delectus aut autem',
                    completed: false,
                    imgAlt: 'Foto Edmar',
                    imgSrc: 'https://via.placeholder.com/150',
                },
                {
                    userId: 1,
                    id: 2,
                    title: 'quis ut nam facilis et officia qui',
                    completed: false,
                    imgAlt: 'Foto Edmar',
                    imgSrc: 'https://via.placeholder.com/150',
                },
                {
                    userId: 1,
                    id: 3,
                    title: 'fugiat veniam minus',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 4,
                    title: 'et porro tempora',
                    completed: true,
                },
                {
                    userId: 1,
                    id: 5,
                    title: 'laboriosam mollitia et enim quasi adipisci quia provident illum',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 6,
                    title: 'qui ullam ratione quibusdam voluptatem quia omnis',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 7,
                    title: 'illo expedita consequatur quia in',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 8,
                    title: 'quo adipisci enim quam ut ab',
                    completed: true,
                },
            ],
            isHome: true,
            pclass: ['text', 'text-home'],
            styleClass: { color: 'aqua', backgroundColor: 'black', 'font-size': '30px' },
            name: 'Jose Edmar',
            sports: 'futebol',
            newsletter: '',
            contract: false,
            colors: [],
            variant: 'danger',
            text: 'Pai: Erro ao enviar'
        };
    },
    components: {
        TheComputada,
        TheObeservador,
        TheLifeCycle,
        BaseCard,
        EnviandoDadoFilho,
    },
    methods: {
        onClick($evt) {
            console.log('click', $evt);
        },
        onMouseOver($evt) {
            console.log('onMouseOver Over', $evt);
        },
        onMouseOut($evt) {
            console.log('onMouseOut Out', $evt);
        },
        onSubmit($evt) {
            console.log('onSubmit com prevent', $evt);
        },
        onKeyUp($evt) {
            console.log('Onkey com prevent', $evt);
        },
    },
};
</script>

<style>
.title {
    font-size: 20px;
    color: blue;
}
.title-home {
    font-size: 50px;
    color: green;
}
.text {
    color: red;
}
.text-home {
    font-size: 35px;
}

.header {
    background: #000;
    color: #fff;
}
.todos-itens {
    background: #000;
    margin: 0 0 5px 0;
    padding: 3px 6px;
    color: #fff;
}
</style>
