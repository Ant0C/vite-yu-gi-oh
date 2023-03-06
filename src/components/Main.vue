<script>
import axios from 'axios';
import Card from './Card.vue';
import Store from '../Store.js';
import Search from './Search.vue';


export default {
    components: {
        Card,
        Search,
    },
    data() {
        return {
            //cards: [],
            Store,
            GetCards() {
                console.log('START MOUNTED')
                const search = this.Store.search
                console.log('store.search = ', search)

                axios
                    .get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                        params: {
                            fname: search,
                            num: 20,
                            offset: 0,
                        }
                    })
                    .then((res) => {
                        console.log(res.data)
                        console.log(res.data.data)
                        this.Store.cards = res.data.data
                        console.log(res.data.meta)
                        this.Store.meta = res.data.meta
                        console.log(this.Store)
                    })
            }

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
                <div class="content">
                    <div class="content-card">
                        <Search @filter="GetCards" />
                        <ul class="cards-gid">
                            <Card v-for="element in Store.cards" :key="element.id" :card="element" />
                            <div>
                                {{ Store.search }}
                            </div>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/general.scss' as *;

main {
    .row {
        display: flex;
        flex-direction: column;
    }

    .container {
        border: solid 2px black;
    }

}

.content {
    background-color: #bf5757;
    padding: 20px;

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
