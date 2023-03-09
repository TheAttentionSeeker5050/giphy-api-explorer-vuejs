<script >
    import { RouterLink, RouterView } from 'vue-router'

    export default {
        props: ['imageURL', 'imageId', "imageTitle","imageAuthor", "currentLocationURL"],
        data() {
            return {
                cardId: `image-card-${this.imageId}`, // this is the unique identifier for an image card
                imagePageURL: `/image/${this.imageId}`,

            }
        },
        components: {
            RouterLink,
            RouterView
        },
        mounted() {

            
        },
        
    }




</script>

<template>
    <section class="image-card" :id='cardId' >
        <img :src='imageURL' :alt="imageTitle" width="200"/>
        <p><RouterLink :id="imageAuthor" :to="imagePageURL">{{imageTitle}}</RouterLink></p>
    </section>
</template>


