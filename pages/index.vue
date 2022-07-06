<template>
  <div>
    <keep-alive>
      <HeroSection>
        <template v-slot:content>
          <div id="page_wrap">
	          <div class="p-5 text-white rounded">
	          	<div class="typed_wrap lg:text-4xl md:text-5xl text-2xl font-bruno">
	          		<vue-typed-js :strings="['Skorsky Blog', 'Kodlamak, bir hayat prensibi!']" :backSpeed="100" 
                  :fadeOut="true" :loop="true" :loopCount="3" :typeSpeed="100">
                  <h1 class="typing"></h1>
                </vue-typed-js>
	          	</div>
	          </div>
          </div>
        </template>
      </HeroSection>
    </keep-alive>

    <div class="mt-10">
      <div class="">
        <div class="px-8">

          <section class="mt-20 w-5/6 lg:w-3/4 md:w-4/5 mx-auto lg:px-4 px-0">
            <div class="font-montserrat font-medium text-4xl mb-10 text-slate-800 mt-20">
              <div class="font-montserrat font-medium text-center text-4xl mb-10 text-slate-800 pt-[60px] pb-[60px] underline  decoration-red-400 decoration-4 underline-offset-8">
                Son Eklenenler
              </div>
            </div>

            <div class="pt-4 grid lg:grid-cols-3 gap-x-8 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

              <HomeBlogCard
                        v-for="article in articles"
                        :key="article.title"
                        :title="article.title"
                        :img="'/covers/'+article.cover"
                        :description="article.description"
                        :date="article.date"
                        :slug="article.slug"
                        :tags="article.tags"
                        :path="article.path"
              />

              <div class="text-center mt-16 lg:hidden block">
                <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                  <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>
                  <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Devamını Oku
                  </span>
                </nuxt-link>
              </div>
            </div>

            <div class="text-center mt-10 lg:block hidden">
              <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Daha Fazlası
                </span>
              </nuxt-link>
            </div>
          </section>

          <section v-if="cyberArticles.length > 0" class="mt-20 w-5/6 lg:w-3/4 md:w-4/5 mx-auto lg:px-4 px-0">
            <div class="font-montserrat font-medium text-4xl mb-10 text-slate-800 mt-20">
              <div class="font-montserrat font-medium text-center text-4xl mb-10 text-slate-800 pt-[60px] pb-[60px] underline  decoration-red-400 decoration-4 underline-offset-8">
                Siber Güvenlik
              </div>
            </div>

            <div class="pt-4 grid lg:grid-cols-3 gap-x-8 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

              <HomeBlogCard
                  v-for="article in cyberArticles"
                  :key="article.title"
                  :title="article.title"
                  :img="'/covers/'+article.cover"
                  :description="article.description"
                  :date="article.date"
                  :slug="article.slug"
                  :tags="article.tags"
                  :path="article.path"
              />

              <div class="text-center mt-16 lg:hidden block">
                <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                  <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                  <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Devamını Oku
                  </span>
                </nuxt-link>
              </div>
            </div>

            <div class="text-center mt-10 lg:block hidden">
              <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Daha Fazlası
                </span>
              </nuxt-link>
            </div>
          </section>

          <section v-if="networkArticles.length > 0" class="mt-20 w-5/6 lg:w-3/4 md:w-4/5 mx-auto lg:px-4 px-0">
            <div class="font-montserrat font-medium text-4xl mb-10 text-slate-800 mt-20">
              <div class="font-montserrat font-medium text-center text-4xl mb-10 text-slate-800 pt-[60px] pb-[60px] underline  decoration-red-400 decoration-4 underline-offset-8">
                Network
              </div>
            </div>

            <div class="pt-4 grid lg:grid-cols-3 gap-x-8 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

              <HomeBlogCard
                  v-for="article in networkArticles"
                  :key="article.title"
                  :title="article.title"
                  :img="'/covers/'+article.cover"
                  :description="article.description"
                  :date="article.date"
                  :slug="article.slug"
                  :tags="article.tags"
                  :path="article.path"
              />

              <div class="text-center mt-16 lg:hidden block">
                <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                  <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                  <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Devamını Oku
                  </span>
                </nuxt-link>
              </div>
            </div>

            <div class="text-center mt-10 lg:block hidden">
              <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Daha Fazlası
                </span>
              </nuxt-link>
            </div>
          </section>

          <section v-if="softwareArticles.length > 0" class="mt-20 w-5/6 lg:w-3/4 md:w-4/5 mx-auto lg:px-4 px-0">
            <div class="font-montserrat font-medium text-4xl mb-10 text-slate-800 mt-20">
              <div class="font-montserrat font-medium text-center text-4xl mb-10 text-slate-800 pt-[60px] pb-[60px] underline  decoration-red-400 decoration-4 underline-offset-8">
                Software
              </div>
            </div>

            <div class="pt-4 grid lg:grid-cols-3 gap-x-8 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

              <HomeBlogCard
                  v-for="article in softwareArticles"
                  :key="article.title"
                  :title="article.title"
                  :img="'/covers/'+article.cover"
                  :description="article.description"
                  :date="article.date"
                  :slug="article.slug"
                  :tags="article.tags"
                  :path="article.path"
              />

              <div class="text-center mt-16 lg:hidden block">
                <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                  <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                  <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Devamını Oku
                  </span>
                </nuxt-link>
              </div>
            </div>

            <div class="text-center mt-10 lg:block hidden">
              <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Daha Fazlası
                </span>
              </nuxt-link>
            </div>
          </section>

          <section v-if="deviceArticles.length > 0" class="mt-20 w-5/6 lg:w-3/4 md:w-4/5 mx-auto lg:px-4 px-0">
            <div class="font-montserrat font-medium text-4xl mb-10 text-slate-800 mt-20">
              <div class="font-montserrat font-medium text-center text-4xl mb-10 text-slate-800 pt-[60px] pb-[60px] underline  decoration-red-400 decoration-4 underline-offset-8">
                Switch & Router
              </div>
            </div>

            <div class="pt-4 grid lg:grid-cols-3 gap-x-8 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

              <HomeBlogCard
                  v-for="article in deviceArticles"
                  :key="article.title"
                  :title="article.title"
                  :img="'/covers/'+article.cover"
                  :description="article.description"
                  :date="article.date"
                  :slug="article.slug"
                  :tags="article.tags"
                  :path="article.path"
              />

              <div class="text-center mt-16 lg:hidden block">
                <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                  <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                  <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Devamını Oku
                  </span>
                </nuxt-link>
              </div>
            </div>

            <div class="text-center mt-10 lg:block hidden">
              <nuxt-link class="relative inline-block group focus:outline-none focus:ring" to="/blog">
                <span class="absolute inset-0 transition-transform translate-x-1.5 translate-y-1.5 bg-pink-300 group-hover:translate-y-0 group-hover:translate-x-0"></span>

                <span class="relative inline-block px-8 py-3 text-sm font-bold tracking-widest text-black uppercase border-2 border-current group-active:text-opacity-75">
                    Daha Fazlası
                </span>
              </nuxt-link>
            </div>
          </section>



        </div>
      </div>
    </div>
  </div>
</template>

<script>
import siteMetaInfo from "@/data/sitemetainfo";
import BlogCard from "~/components/Blog/BlogCard";
import BlogCardHorizontal from "~/components/Blog/BlogCardHorizontal";
import HeroSection from "~/components/Common/HeroSection";
import VueTypedJs from "vue-typed-js"
import Vue from "vue";

Vue.use(VueTypedJs)

export default {
  components: {
    HeroSection,
    BlogCard,
    BlogCardHorizontal,
    },
  data() {
    return {
      siteMetaInfo: siteMetaInfo,
    };
  },


  async asyncData({ $content, params, route }) {
    const articles = await $content("articles", {deep: true}, params.slug)
      .only([
        "title",
        "description",
        "img",
        "slug",
        "tags",
        "author",
        "date",
        "path",
        "cover"
      ])
      .limit(3)
      .sortBy("date", "desc")
      .fetch();

    const networkArticles = await $content("articles", {deep: true}, params.slug)
        .only([
          "title",
          "description",
          "img",
          "slug",
          "tags",
          "author",
          "date",
          "path",
          "cover"
        ])
        .where( { categories: { $contains: "Network" } } )
        .limit(3)
        .sortBy("date", "asc")
        .fetch();

    const deviceArticles = await $content("articles", {deep: true}, params.slug)
        .only([
          "title",
          "description",
          "img",
          "slug",
          "tags",
          "author",
          "date",
          "path",
          "cover"
        ])
        .where( { categories: { $contains: "Switch & Router" } } )
        .limit(3)
        .sortBy("date", "asc")
        .fetch();

    const cyberArticles = await $content("articles", {deep: true}, params.slug)
        .only([
          "title",
          "description",
          "img",
          "slug",
          "tags",
          "author",
          "date",
          "path",
          "cover"
        ])
        .where( { categories: { $contains: "Siber Güvenlik" } } )
        .limit(3)
        .sortBy("date", "asc")
        .fetch();

    const softwareArticles = await $content("articles", {deep: true}, params.slug)
        .only([
          "title",
          "description",
          "img",
          "slug",
          "tags",
          "author",
          "date",
          "path",
          "cover"
        ])
        .where( { categories: { $contains: "Software" } } )
        .limit(3)
        .sortBy("date", "asc")
        .fetch();

    return {
      articles,
      networkArticles,
      deviceArticles,
      cyberArticles,
      softwareArticles
    };
  },
  head: {
    title: siteMetaInfo.title,
    meta: [
      {
        hid: "description",
        name: "description",
        content: siteMetaInfo.description,
      }

    ],
  },
};
</script>

<style lang="scss" scoped>

.writing-vertical {
  writing-mode: vertical-rl;
}

#c {
  transition: opacity 1500ms ease-out;
}

.clip-ellipse {
  clip-path: ellipse(60% 100% at 50% 0%);
  @apply bg-white;
  height: 100px;
  width: 100%;

}
</style>
