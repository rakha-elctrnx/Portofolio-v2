<template>
  <div class="container mx-auto p-3 md:p-8">
    <div class="flex flex-col-reverse md:flex-row relative">
      <div class="w-full md:w-2/3 overflow-y-auto">
        <div class="flex flex-col gap-4 md:px-20">
          <article v-for="articles in article" :key="article.id"
            class="flex w-full bg-[#1e1e1f] border-[#383838] rounded-xl text-left text-white p-5 md:py-7 md:px-8 cursor-pointer hover:bg-[#282828] item-card items-center">
            <div class="w-full pr-4">
              <div class="text-xs mb-1 text-slate-400 flex items-center">
                <div class="h-[1px] w-20 bg-amber-200 md:w-5 aos-init aos-animate mr-2" data-aos="zoom-in-left"
                  data-aos-duration="600"></div> 17 Juli, 2020
              </div>
              <h1 class="text-sm md:text-md text-amber-200 font-bold mb-2">Why I’m sticking with Vue in 2023</h1>
              <p class="text-sm hidden md:block">After years of vue application development, I was about to jump ship to
                Svelte. In the end, I didn't, here is why. — I started using Vue professionally somewhere around 2018,
                coming from angular. It has...</p>
            </div>
            <div>
              <div class="w-20 h-20 md:w-28 md:h-28">
                <img src="https://loremflickr.com/200/200/abstract" class="rounded-lg md:rounded-xl" alt="">
              </div>
            </div>
          </article>

        </div>
      </div>
      <div class="w-full md:w-1/3 h-fit p-8 md:sticky md:top-24">
        <!-- Sidebar -->
        <div class="flex flex-col text-left">
          <div class="bg-clip-text bg-gradient-to-r from-slate-100 to-amber-300 text-transparent">Let's share experiences,
            stories, and knowledge together.
          </div>
          <div class="h-[1px] mt-7 mb-7 w-20 bg-amber-200 aos-init aos-animate mr-2"></div>
          <div class="hidden md:block">
            <div class="text-white text-md font-semibold">Topics</div>
            <div class="mt-3 flex flex-wrap gap-1">
              <span class="py-2 px-3 rounded-2xl bg-[#1e1e1f] hover:bg-white/20 text-white text-xs cursor-pointer">VueJS</span>
              <span class="py-2 px-3 rounded-2xl bg-[#1e1e1f] hover:bg-white/20 text-white text-xs cursor-pointer">Technology</span>
            </div>
            <div class="h-[1px] mt-7 mb-7 w-20 bg-amber-200 aos-init aos-animate mr-2"></div>
            <div class="text-white text-md font-semibold">Popular Articles</div>

          </div>
        </div>
      </div>
    </div>
  </div>
  <ArticleList />
</template>
  
<script>
import ArticleList from '@/components/ArticleList.vue';
import axios from "axios";
export default {
  data() {
    articles: []
  },
  components: {
    ArticleList
  },
  mounted() {

  },
  methods: {
    async getArticles() {
      axios.get('/')
      .then(response => {
        this.articles = response.data;
      })
    }
  }
}

</script>

<style></style>