<template>
  <div class="md:fixed">
    <div class="md:block flex mobile-justify items-center">
      <nuxt-img
        :src="siteMetadata.author_image"
        loading="lazy"
        alt="me"
        class="h-45 w-30 ml-8"
      />
    </div>
    <div class="mb-2 mx-7 mt-4 text-center">
      <h1
          class="md:text-3xl text-2xl text-gray-800 font-bold dark:text-blue-100"
      >
        {{ siteMetadata.author }}
      </h1>
      <div class="md:text-lg text-gray-600 dark:text-blue-100 text-left mobile-center">
        {{ siteMetadata.position }}
      </div>
      <a
          :href="`mailto:${siteMetadata.email}`"
          class="text-gray-600 md:hidden mt-1 dark:text-blue-100"
      >
        {{ siteMetadata.email }}
      </a>
    </div>

    <div class="mx-7 hidden md:block">
      <div class="my-2 text-gray-600 flex dark:text-blue-100">
        <Mail />
        <a class="ml-2" :href="`mailto:${siteMetadata.email}`"> {{ siteMetadata.email }}</a>
      </div>
      <div class="my-2 text-gray-600 flex dark:text-blue-100">
        <Glob />
        <a class="ml-2" :href="siteMetadata.personalWebSite"> Portfolyo </a>
      </div>
      <div class="my-2 text-gray-600 flex dark:text-blue-200">
        <Github />
        <a class="ml-2" :href="siteMetadata.github"> {{ siteMetadata.githubUser }}</a>
      </div>
      <div class="my-2 text-gray-600 flex dark:text-blue-200">
        <Linkedin />
        <a class="ml-2" :href="siteMetadata.linkedin"> {{ siteMetadata.linkedinUser }}</a>
      </div>
    </div>
  </div>
</template>

<script>
import Mail from "~/assets/icon/mail.svg?inline";
import Glob from "~/assets/icon/glob.svg?inline";
import Twitter from "~/assets/icon/twitter.svg?inline"
import Github from "~/assets/icon/github_new.svg?inline";
import Linkedin from "~/assets/icon/linkeding.svg?inline"
import siteMetaInfo from "~/data/sitemetainfo";
export default {
  components: { Mail, Glob, Github, Linkedin, Twitter },
  data: () => {
    return {
      siteMetadata: siteMetaInfo,
    };
  },
};
</script>

<style scoped>
@media screen and (min-width: 768px) {
  .mobile-justify{
    justify-content: center;
  }
  mobile-left{
    text-align: left;
  }
}
@media screen and (max-width: 768px) {
  .mobile-center{
    text-align: center;
  }
}
</style>
