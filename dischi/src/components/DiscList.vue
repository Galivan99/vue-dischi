<template>
    <div class="sfondo">
        <div class="ric">
            <Ricerca @effettuaRicerca="ricercaSet"/>
        </div>
        <div class="container">
            <div class="x" v-for="(disco, index) in listaDischiFiltered" :key="index">
                <DiscoItem :item="disco" />
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import DiscoItem from "../components/DiscoItem.vue";
import Ricerca from "../components/Ricerca.vue"


export default {
    name: 'DiscList',
    components: {
        DiscoItem,
        Ricerca
    },
    data() {
        return {
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            listaDischi: [],
            listaDischiFiltered: [],
        }
    }, 
    created() {
        this.dischi();
    },

    methods: {
        dischi() {
            axios
                .get(this.url)
                .then(risposta => {
                    console.log(risposta.data.response)
                    this.listaDischi = risposta.data.response;
                    this.listaDischiFiltered = this.listaDischi;
                })
        },
        ricercaSet(option) {
            if(option == "tutto") {
                this.listaDischiFiltered = this.listaDischi;
            }
            else {
                this.listaDischiFiltered = this.listaDischi.filter(x => x.genre == option);
            }  
        }
    }
}
</script>

<style scoped lang="scss">
    .sfondo {
        width: 100%;
        height: calc(100vh - 100px);
        background-color: #1E2D3B; 

        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: flex-start;
            align-items: center;
            width: 950px;
            height: 100%;
            margin: 0 auto;

            .x {
                display: flex;
                justify-content: center;
                align-items: center;
                width: 170px;
                height: 250px;
                background-color: #2E3A46;
                margin-left: 10px;
                margin-right: 10px;
            }
        }
    }

    .ric {
        position: absolute;
        top: 120px;
        left: 44%;
    }
</style>