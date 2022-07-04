<template>
  <div class="mt-10">
    <div class="font-montserrat font-medium text-center text-4xl text-slate-800 pt-[60px] underline
      decoration-red-400 decoration-4 underline-offset-8 mt-6">
      Blog
    </div>
    <div class="flex flex-col items-start sm:flex-row pt-12">
      <aside class="hidden px-6 py-6 space-y-8 sm:block w-[200px]" aria-label="Sidebar">
        <div class="sidebar">
          <div class="side-wrapper">
            <div class="side-menu">
              <a class="sidebar-link" :class ="{ active : currentTag==category }" href="#" v-for="category in allCategories" :key="category" @click.prevent="changeCategory(category)" >
                {{ category }}
              </a>
            </div>
          </div>
        </div>
      </aside>
      <div>
        <div class="grid xl:grid-cols-5 lg:grid-cols-3 gap-x-3 md:grid-cols-2 sm:grid-cols-1 items-stretch m-3">

          <BlogCard @changeCurrentTag="(tag) => currentTag = tag"
                    v-for="article in articles"
                    :currentTag="currentTag"
                    :key="article.title"
                    :title="article.title"
                    :img="'/covers/'+article.cover"
                    :description="article.description"
                    :date="article.date"
                    :slug="article.slug"
                    :tags="article.tags"
                    :path="article.path"
                    :categories="article.categories"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import siteMetaInfo from "@/data/sitemetainfo";
import HeroSection from "~/components/Common/HeroSection";

export default {
  components: {HeroSection},
  methods : {
    changeCategory(category){
      if(this.currentTag == category){
        this.currentTag = "this.$route.query.tag || ''"
      }
      this.currentTag = category
    }
  },
  data() {
    return {
      currentTag: this.$route.query.tag || ''
    }
  },
  async asyncData({$content, params, route}) {
    const categories = await $content("articles", {deep: true}, params.slug)
      .only([
        "categories",
      ])
      .fetch();
    let allCategories = [];
    categories.forEach(category => {
      if ("categories" in category) {
        category.categories.forEach(category => {
          if (!allCategories.includes(category)) {
            allCategories.push(category);
          }
        });
      }
    });
    allCategories.sort()

    let looker = $content("articles", {deep: true}, params.slug)
      .only([
        "title",
        "description",
        "img",
        "slug",
        "tags",
        "author",
        "date",
        "draft",
        "path",
        "cover",
        "categories"
      ])
      .sortBy("date", "desc");

    const articles = await looker.fetch();

    return {
      articles, allCategories
    };
  },
  head: {
    title: siteMetaInfo.title,
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap");

* {
  outline: none;
  box-sizing: border-box;
}

html {
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
}

img {
  max-width: 100%;
}

:root {
  --body-font: "Inter", sans-serif;
  --theme-bg: #1f1d2b;
  --body-color: #808191;
  --button-bg: #353340;
  --border-color: rgb(128 129 145 / 24%);
  --video-bg: #252936;
  --delay: 0s;
}

.active{
  background-color: #53304d;
  transition: 0.35s cubic-bezier(0.25, 0.1, 0, 2.05);
  color: #ffffff;
  padding: 7px;
  border-radius: 5px;
}

.sidebar {
  width: 220px;
  height: 100%;
  padding-left: 15px;
  display: flex;
  flex-direction: column;
  flex-shrink: 0;
  transition-duration: 0.2s;
  overflow-y: auto;
  overflow-x: hidden;
  &-link {
    &:hover{
      background-color: #53304d;
      transition: 0.35s cubic-bezier(0.25, 0.1, 0, 2.05);
      color: #fff;
      padding: 7px;
      border-radius: 5px;
    }
  }


  &.collapse {
    width: 90px;
    border-right: 1px solid var(--border-color);
    .logo-expand,
    .side-title {
      display: none;
    }
    .side-wrapper {
      width: 30px;
    }
  }
}


.side-menu {
  display: flex;
  flex-direction: column;
  a {
    display: flex;
    align-items: center;
    text-decoration: none;
    & + a {
      margin-top: 26px;
    }
  }
}

.side-title {
  font-size: 12px;
  letter-spacing: 0.07em;
  margin-bottom: 24px;
}

.side-wrapper {
  border-bottom: 1px solid var(--border-color);
  width: 145px;
  & + & {
    border-bottom: none;
  }
}

.wrapper {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.header {
  display: flex;
  align-items: center;
  flex-shrink: 0;
  padding: 30px;
}

</style>
