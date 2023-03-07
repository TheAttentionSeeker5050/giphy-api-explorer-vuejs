<script >

import SearchResultsContainer from "@/components/SearchResults.vue"

export default {
  data() {
    return {
      searchText: '',
      searchResult: null,
      searchError: ''
    }
  },
  mounted() {

  },
  methods: {
    onSearchEvent() {
      // test that my state and input actually works
      // alert("displaying results for:"+this.searchText);

      // fetch result data
      fetch(`https://api.giphy.com/v1/gifs/search?api_key=Vf0EMF6nc67havZHyJ8oVtErI9Ms4QCB&q=${this.searchText}&limit=25&offset=0&rating=g&lang=en`)
        .then(response => response.json())
        .then(data => this.searchResult = data)
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
  <main id="main-container">
    
    <h2>Title here</h2>

    <form id="search-image-section" @submit.prevent="onSubmit">
      <input type="text"  id="img-search-input"
      v-model="searchText">
      <button id="submit-btn" @click="onSearchEvent()">
        <img src="https://img.icons8.com/ios/50/null/search--v1.png" width="20" />
      </button>
    </form>

    <section id="results-section">
      <p v-if="searchResult">
        Displaying results for {{searchText}}:
      </p>

      <SearchResultsContainer/>

      <p v-if="searchError">Error: <br> {{searchError}}</p>

      
    </section>

    
  </main>
</template>
