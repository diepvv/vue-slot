<template>
    <div>
        <li v-for="link in links" :key='link'>
            <slot name="link"
                :link="link"
                :bookmark="bookmark"
                :bookmarkButtonEvents="{
                    click: () => bookmark(link)
                }"
            ></slot>
        </li>
        <div class="card-header">
            <slot name="header"></slot>
        </div>
        <div class="card-body">
            <slot name="body"></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChildTag',
    data() {
        return {
        links: [
            { href: 'https://www.facebook.com/NuNu06081995', title: 'First Link', bookmarked: true },
            { href: 'https://genk.vn/', title: 'Second Link', bookmarked: false },
        ]
        }
    },
    methods: {
     bookmark(link) {
       link.bookmarked = !link.bookmarked
    }
  }
}
</script>

<style>

</style>