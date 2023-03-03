<script>
import axios from 'axios';
import { Store } from '../Store.js';
import Card from './Card.vue';

export default {
    components: {
        Card,

    },
    data() {
        return {
            info: {},
            Store,
        }
    },
    computed: {
        cards() {
            return this.Store.cards
        }
    },
    methods: {
        GetCards() {
            console.log('START MOUNTED')
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
                .then((res) => {
                    console.log(res)
                    console.log(res.data)
                    this.Store.cards = res.data
                    //this.store.name = res.data.info
                    // this.store.pages = pages
                    console.log(this.Store)
                })
        }
    },
    created() {
        console.log(this.Store)
        this.GetCards()
    },
}

</script>

<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="select">
                    alien
                </div>
                <div class="content">
                    <div class="container">
                        <div class="content-info">
                            number
                        </div>
                        <div class="content-card">
                            <Card v-for="element in Store.cards" :key="element.id" :card="element"></Card>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;

main {
    background-color: burlywood;
    min-height: 800px;

    .row {
        display: flex;
        flex-direction: column;
    }
}

.select {
    padding: 10px;
}

.content {
    background-color: white;
    min-height: 500px;
    padding: 20px;

    .content-info {
        background-color: rgb(36, 35, 35);
        color: white;
        padding: 10px;
    }
}
</style>
