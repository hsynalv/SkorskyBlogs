<template>
  <div v-if="isFiltered" class="mb-4 bg-white border border-gray-200 min-h-[400px] border-b-2 border-b-slate-400
  hover:drop-shadow-xl hover:border-gray-300 transition-all hover:-translate-y-1">
    <nuxt-link class="overflow-hidden " :to="postLink">
      <img
        v-if="img"
        class="object-cover w-full h-52"
        :src="'/images/' + img"
        alt=""
      />
      <img
        v-else
        class="object-contain w-full h-52"
        src="/images/post-anonymous.jpg"
        alt=""
      />
    </nuxt-link>
      <div class="p-3">
        <div class="text-xs text-slate-400 left-2">
          {{ formatDate(postDate)}}
        </div>
        <h5 class="text-lg font-bold ">
          <nuxt-link class="overflow-hidden " :to="postLink">
          {{ postTitle }}
          </nuxt-link>
        </h5>

        <p class="mt-2 text-[12px] my-3 flex flex-wrap -m-1 text-overflow">
          <nuxt-link @click.prevent="$emit('changeCurrentTag', tag)"
                     v-for="tag in tags"
                     :key="tag"
                     to="/blog"
                     class="m-1 leading-loose text-slate-400 border border-current lowercase px-2 rounded font-medium"
                     tag="a"
          >#{{tag}}</nuxt-link>
        </p>
      </div>

    <div class="center">
      <nuxt-link class="relative inline-block group focus:outline-none focus:ring" :to="postLink">
        <span class="custom-radius absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>
        <span class="relative inline-block px-3 py-1 text-sm font-bold tracking-widest text-black uppercase custom-border border-current group-active:text-opacity-75">
           Devamını Oku
      </span>
      </nuxt-link>
    </div>



  </div>
</template>
<script>
export default {
  name: 'BlogCard',
  props: ["title", "description", "date", "slug", "path", "img", "tags", "currentTag"],
  emits: ['changeCurrentTag'],
  data() {
    return {
      postTitle: this.title,
      postDescription: this.description,
      postSlug: this.slug,
      postDate: this.date,
      postLink: this.path.replace("articles/", ""),
    };
  },
  computed: {
    isFiltered() {
      return !this.currentTag || (this.tags && this.tags.includes(this.currentTag));
    },
  },
  methods: {
    formatDate(date) {
      return new Date(date).toLocaleDateString("tr", {
        weekday: 'short', year: 'numeric', month: 'short',
        day: 'numeric'
      });
    },
  },
}
</script>
<style scoped>
.custom-border{
  border-width: 1.5px;
  border-radius: 5px;
}
.custom-radius{
  border-radius: 5px;
  -moz-border-radius: 5px;
}
.center{
  align-items: center;
  text-align: center;
}
.text-overflow{
  overflow: hidden;
}
</style>
