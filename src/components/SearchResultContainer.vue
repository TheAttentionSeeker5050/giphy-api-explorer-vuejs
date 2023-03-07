<script >
export default {
    props: ['imageURL', 'imageId', "imageTitle"],
    data() {
        return {
        cardId: `image-card-${this.imageId}`, // this is the unique identifier for an image card
        }
    },
    
}




</script>

<template>
    <section class="image-card" :id='cardId' >
        <img :src='imageURL' width="200"/>
        <p>{{imageTitle}}</p>
    </section>
</template>


