<template>
  <footer class="lg:mt-52 border-t border-t-2">
    <div class="flex flex-col items-center mt-16">
      <div class="flex mb-3 space-x-4">
        <a
          target="_blank"
          :href="siteMetadata.personalWebSite"
          class="text-sm text-gray-500 transition hover:text-gray-600"
        >
          <img class="transition-transform hover:scale-110 w-8 h-8" src="../assets/icon/glob.svg"/>
        </a>
        <a
          class="text-sm text-gray-500 transition hover:text-gray-600"
          target="_blank"
          rel="nofollow noopener noreferrer"
          :href="siteMetadata.github"
          ><span class="sr-only">github</span>
          <img class="transition-transform hover:scale-110 w-8 h-8" src="../assets/icon/github_new.svg" /> </a
        ><a
          class="text-sm text-gray-500 transition hover:text-gray-600"
          target="_blank"
          rel="noopener noreferrer"
          :href="siteMetadata.linkedin"
          ><span class="sr-only">Linkedin</span>
          <img class="transition-transform hover:scale-110 w-8 h-8" src="../assets/icon/linkeding.svg" /> </a
        >
        <a
          target="_blank" rel="nofollow noopener noreferrer"
          :href="siteMetadata.twitter + siteMetadata.twitter_user"
          class="text-sm text-gray-500 transition hover:text-gray-600"
        >
          <img class="transition-transform hover:scale-110 w-8 h-8" src="../assets/icon/twitter.svg"/>
        </a>

      </div>
      <div class="text-center mobile-flex mb-2 space-x-2 text-sm text-gray-500 dark:text-gray-400">
        <div>Copyright © {{ new Date().getFullYear() }}</div>
        <div>•</div>
        {{ siteMetadata.title }} - {{ siteMetadata.slogan }}
      </div>
    </div>
  </footer>
</template>

<script>
import siteMetaInfo from "~/data/sitemetainfo";
export default {
  data() {
    return {
      siteMetadata: siteMetaInfo,
    };
  },
};
</script>

<style scoped>
@media screen and (min-width: 768px) {
  .mobile-flex{
    display: flex;
  }
}
</style>
