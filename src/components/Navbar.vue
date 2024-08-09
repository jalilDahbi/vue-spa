<template>
         <nav
                class="navbar navbar-expand-lg"
                :class="[`navbar-${theme} bg-${theme}`]"
                >
                    <div class="container">
                        <a class="navbar-brand" href="#">vue bisic</a>

                        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li v-for="(page, index) in pages" class="nav-item" :key="index">
                            <a
                            @click.prevent="navLinkClick(index)"
                            class="nav-link"
                            :class="{active: activePage == index}"
                            aria-current="page"
                            :href="page.link.url"
                            :title="`you are going to ${page.link.text} page`"
                            >
                            {{page.link.text}}
                            </a>
                        </li>
                        </ul>
                        <form class="d-flex">
                        <button class="btn btn-primary" @click.prevent="changeTheme()">
                            toggle to nav
                        </button>
                        </form>
                    </div>
                </nav>

</template>
<script>
export default {
    props: ['pages','activePage', 'navLinkClick'],
    data(){
            return {
                theme: "light",
            }
        },
         methods:{
            changeTheme() {
            this.theme = this.theme === "light" ? "dark" : "light";
          },
        }
}
</script>