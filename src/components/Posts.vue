<template>
    <div class="container">
        <h2>My Posts</h2>
        <div class="posts">
            <div class="post" v-for="(post, index) in posts" :key="index">
                <h3>{{ post.title }}</h3>
                <span>{{ post.views }} Views</span>
            </div>
        </div>
        <div class="totals">
            <strong>{{ allPostViews }} Total Views</strong>
        </div>
        <div class="button">
            <button @click="createPost">Create New Post</button>
        </div>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
interface Post {
    title: string,
    views: number,
    reduce?: any,
    push?: any,
};
export default defineComponent({
    props: {
        posts: {
            type: Object as () => Post,
            required: true
        }
    },
    data() {
        return {
            
        }
    },
    methods: {
        createPost() {
            // add a new post to the posts array
            let post: Post = {
                title: "Hello, world!",
                views: 52
            };

            this.posts.push(post);
        }
    },
    computed: {
        allPostViews(): number {
            return this.posts.reduce((acc: number, post: Post) => acc += post.views, 0);
        }
    }
})
</script>
<style>
.post {
    margin-bottom: 1rem;
}
.post h3 {
    margin-bottom: 0;
}
</style>