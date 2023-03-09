<script  >
    export default {
        props: ['nextPageLink', 'prevPageLink'],
        data() {
        return {

        }
  },
    
    }
</script>

<template>
    <section id="pagination-section" >
      <span>
        <a v-if="prevPageLink" :href="prevPageLink">&lt;&lt;Previous page</a>
        <div class="grayed-out" v-else="prevPageLink">
            &lt;&lt;Previous page
        </div>
      </span>
      <span>
        <a v-if="nextPageLink" :href="nextPageLink" >Next page&gt;&gt;</a>
        
      </span>
    </section>
</template>


<style scoped>

</style>