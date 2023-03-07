<script >

import SearchResultsContainer from "@/components/SearchResultContainer.vue"

export default {
  data() {
    return {
      searchText: this.$route.query.query,
      searchResult: null,
      searchError: '',
      pageNumber: this.$route.query.page || 1,
      pagination: this.$route.query.pagination || 20,
      

    }
  },
  mounted() {
    
    if (this.searchText) {
      this.onSearchEvent()
    }
  },
  methods: {
    onSearchEvent() {
      let pageNumber = this.pagination*this.pageNumber+1
      console.log("offset:", pageNumber)

      // fetch result data
      fetch(`https://api.giphy.com/v1/gifs/search?api_key=Vf0EMF6nc67havZHyJ8oVtErI9Ms4QCB&q=${this.searchText}&limit=${this.pagination}&offset=${pageNumber}&rating=g&lang=en`)
        .then(response => response.json())
        .then(data => this.searchResult = data.data) // the searchResult value is an array
        .catch(error => this.searchError = error)

    }
  },
  components: {
    // sub components
    SearchResultsContainer
  }
}

</script>

<template>
  <main id="main-container" class="search-results">
    
    <h2>Search Images</h2>

    <form id="search-image-section" @submit.prevent="onSubmit">
      <input type="text"  id="img-search-input"
      v-model="searchText" >
      <button id="submit-btn" @click="onSearchEvent()">
        <img src="https://img.icons8.com/ios/50/null/search--v1.png" width="20" />
      </button>
    </form>

    <!-- when the results appear, this section will display -->

    <section id="results-section" v-if="searchResult">
      <p v-if="searchResult" id="search-results-title">
        Displaying results for {{searchText}}:
      </p>

      <!-- <p id="horizontal-line"></p> -->

      <div id="search-results-wrapper" >
        <SearchResultsContainer 
          v-for="image in searchResult"
          :key="image.id"
          :imageId="image.id"
          :imageURL="image.images.original.url"
          :imageTitle="image.title"
        />
      </div>


      <p v-if="searchError">Error: <br> {{searchError}}</p>

      <!-- pagination -->
      
    </section>

    
  </main>
</template>


<style lang="scss" >

</style>