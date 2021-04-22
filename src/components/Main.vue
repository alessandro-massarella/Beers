<template>
<div>
    <div class="search">
        <input type="text" v-model="myQuery" placeholder="SEARCH A BEER">
        <button @click="mySearch">Search</button>
    </div>
    

    <div class="container">
        <div class="my_card" v-for="beer in info" :key="beer.id">
                <router-link
                    :to="{ name: 'Details', 
                                params: {
                                    id: beer.id, 
                                    name: beer.name,
                                    brewery_type: beer.brewery_type,
                                    address: beer.street,
                                    city: beer.city,
                                    state: beer.state,
                                    country: beer.country,
                                    website: beer.website_url}}" >
                            <h3><a href="" target="_blank"> {{ beer.name }} </a></h3> 
                </router-link>
            <p>
                <em>Brewery type:</em> {{ beer.brewery_type}} <br>
                <em></em>
            </p>

        </div>
    </div>
</div>
  
</template>

<script>
import axios from "axios"

export default {
    name: 'Main',

    data() {
        return {
            info: null,
            myQuery: null
        }

        
    },

    methods: {
        mySearch: function() {
            
            axios
            .get('https://api.openbrewerydb.org/breweries/search', {
                params: {
                    'query':this.myQuery

                }
            })
            .then(response => (this.info = response.data))






        }
            

    }
    

}
</script>

<style>
    a {
        text-decoration: none;
        color: rgb(196, 139, 74)
    }


    .my_card {
        min-width: 300px;
        max-width: 300px;
        min-height: 100px;
        /* border: 1px solid orangered; */
        margin: 10px;
        padding: 10px;
        /* border-radius: 5px; */
        background-color: white;

        box-shadow: 5px 5px 10px 2px #333333;
        
        
    }

    .container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        /* justify-content: center; */
        align-items: center;

    }

    .search {
        margin-top: 20px;
    }

    .search button {
        border-radius: 10px;
        /* border: 1px solid black; */
        padding: 1px;
        background-color: rgba(26, 163, 26, 0.082);
        height: 40px;
        width: 50px;
        margin-left: 10px;

    }

    .search input {
        border: 0em;
        height: 40px;
        width: 400px;
        border-radius: 20px;
        box-shadow: 5px 5px 10px 2px #333333;
        padding: 10px;

    }

    .search h3 {
        color: black;
    }


</style>