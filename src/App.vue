<template>
  <navbar 
    :pages="pages" 
    :active-page="activePage"
    :nav-link-click="(index) => activePage = index"
    >

    </navbar>
  <page-viewer :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from './components/PageViewer.vue'
import Navbar from './components/Navbar.vue'
  export default {
    components:{
      PageViewer,
      Navbar
    },
    data() {
          return {
            useNavDark: false,
            activePage: 0,
            pages: [
              {
                link: { text: "home", url: "index.html" },
                content: "this is home page",
                title: "home page",
              },
              {
                link: { text: "about", url: "about.html" },
                content: "this is about page",
                title: "about page",
              },
              {
                link: { text: "contact", url: "contact.html" },
                content: "this is contact page",
                title: "contact page",
              },
            ],
          };
        }
  }
</script>

<style>

</style>
