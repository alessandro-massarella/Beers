<template>
    <div class="details_page">
        <!-- <p>{{ id }}</p> -->
        <h1>{{ name }}</h1>
        <p> <b>City:</b> {{ city }}</p>
        <p> <b>Brewery Type:</b> {{ brewery_type }}</p>
        <p><b>Address:</b> {{ address }}</p>
        <p><b>State:</b> {{ state }}</p>
        <p><b>Country:</b> {{ country }}</p>
        <a :href="website" target="_blank">Site</a>
    </div>
  
</template>

<script>
export default {
    props: ['id', 'name', 'city', 'brewery_type', 'address', 'state', 'country', 'website']
}
</script>

<style>
    .details_page {
        background-color: honeydew;
        width: 400px;
        padding: 10px;

        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%); 


    }

</style>