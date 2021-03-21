<template>
<div>
    <h2>{{msg}}</h2>
    <ChildTag>
        <div slot="link" slot-scope="{ link, bookmarkButtonEvents }">
            <p v-show="link.bookmarked">Bookmarked True</p>
            <p v-show="link.bookmarked === false">Bookmarked False</p>
            <a :href="link.href">{{ link.title }}</a>
            <button class="btn-bookmark" v-on="bookmarkButtonEvents">Bookmark</button>
        </div>
        <h1 slot="header">Nu vivu header</h1>
        <div slot="body">
            <h5>Nu Nu body1</h5>
            <p>Nu Nu body2</p>
        </div>
    </ChildTag>
    
</div>
</template>

<script>
import ChildTag from './child.vue'
export default {
name: 'ParentTag',
data()  {
    return {
        msg: 'Layout Parent Tag'
    }
},
components: {
   ChildTag
}
}
</script>

<style>
.btn-bookmark {
    margin-left: 2%;
}
</style>