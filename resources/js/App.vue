<template>
    <div class="container">
        <ul>
            <li
                v-for="post in posts"
                :key="post.id">
                <h3>{{post.title}}</h3>
                <p>{{post.content}}</p>
            </li>
        </ul>
    </div>
</template>

<script>

export default {
    name: "App",
    data(){
        return {
            apiUrl: "/api/posts",
            posts: null
        }
    },
    methods: {
        getApi(){
            axios.get(this.apiUrl)
                .then(res=>{
                    this.posts = res.data;
                })
        }
    },
    mounted(){
        this.getApi();
    }
}
</script>

<style>

</style>
