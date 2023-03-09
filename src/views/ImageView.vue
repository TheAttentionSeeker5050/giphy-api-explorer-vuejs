<template>
    <main id="image-view-container">
        

        <h2>{{imageTitle}}</h2>


        <section id="error-page" v-if="searchError">
            <p>Sorry, we had issues pulling the image's data</p>
            <p>{{searchError}}</p>
            
        </section>
        
        <!-- in case there is not error page, display the following wrapper -->
        <div id="get-image-data-wrapper" v-else="searchError">
            <section id="image-section" >
                <img  :src='imageURL' :alt='imageType' />
                <p>{{imageTitle}}</p>
            
            </section>

            <section id="image-description-section">
                <p><span>Type:</span> {{imageType}}</p>
                <p><span>Author:</span> {{imageAuthor}}</p>
                <p>
                    <span>Author Giphy profile URL: </span>
                    <a :href="imageAuthorURL">{{imageAuthorURL}} </a>
                    
                </p>
                <p><span>Content rating:</span> {{imageRating}}</p>
                <p><span>Upload date:</span> {{imageDate}}</p>

                <button @click="goBackToPreviousPage()">Go back to search </button>
            </section>

            
        </div>
    </main>
</template>

<script >
    import { RouterLink } from 'vue-router'
    export default {
        data() {
            return {
                searchResult: null,
                imageId: this.$route.params.id,
                searchError: '',
                imageAuthor: '',
                imageAuthorURL:'',
                imageAuthorAvatar: '',
                imageTitle: '',
                imageRating: '',
                imageDate: '',
                imageURL: '',
                imageType:''
            }
        },
        mounted() {
            

            if (this.$route.params.query) {
                this.prevPage = this.$route.params.query.prevPage
            }

            fetch(`https://api.giphy.com/v1/gifs/${this.imageId}?api_key=Vf0EMF6nc67havZHyJ8oVtErI9Ms4QCB`)
            
                .then(response => response.json())
                .then(data => {
                    this.imageTitle = data.data.title;
                    this.imageURL = data.data.images.fixed_width_still.url;
                    this.imageType = data.data.type;
                    this.imageAuthor = data.data.username || "Unknown";
                    if (data.data.user) {
                        this.imageAuthorURL = data.data.user.profile_url ;
                    } else {
                        this.imageAuthorURL = "N/A";
                    }
                    this.imageRating = data.data.rating;
                    this.imageDate = data.data.import_datetime;

                }) // the searchResult value is an array
                .catch(error => this.searchError = error)
        },
        methods: {
            goBackToPreviousPage() {
                this.$router.go(-1)
            }
        }


    }
    

    
</script>

<style lang="scss" >
    @import "./../assets/imageView.scss";
</style>