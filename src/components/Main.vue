<script>
import axios from 'axios';
import Card from './Card.vue';

export default {
    components: {
        Card,

    },
    data() {
        return {
            cards: [],
            info: {}
        }
    },
    methods: {
        GetCards() {
            console.log('START MOUNTED')
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0')
                .then((res) => {
                    console.log(res.data)
                    console.log(res.data.data)
                    this.cards = res.data.data
                    console.log(this.cards)
                })
        }
    },
    created() {
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
                        <div class="container content-card">
                            <ul class="cards-gid">
                                <!-- <li class="row card" v-for="card in cards" :key="card.id">
                                                <img :src="card.card_images[0].image_url" alt="">
                                                <span class="card-name">
                                                    {{ card.name }}
                                                </span>
                                                <span class="card-archetype">
                                                    {{ card.archetype }}
                                                </span>
                                            </li> -->

                                <Card v-for="element in cards" :key="element.id" :card="element"></Card>
                            </ul>
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
    padding: 20px;

    .content-info {
        background-color: rgb(36, 35, 35);
        color: white;
        padding: 10px;
    }

    .content-card {
        margin-top: 20px;
    }
}

.cards-gid {
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(5, 1fr);
}
</style>
