<template>
    <div class="app">
        <h1>Страница с постами</h1>
        <my-button @click="showDialog">Создать пост</my-button>
        <my-dialog v-model:show="dialogVisible">
            <PostForm @create="createPost" />
        </my-dialog>
        <div>
            <PostList :posts="posts" @remove="removePost" />
        </div>
    </div>
</template>

<script>
    import PostForm from "@/components/PostForm";
    import PostList from "@/components/PostList";
    export default {
        components: {
            PostForm,
            PostList,
        },
        data() {
            return {
                posts: [
                    {
                        id: 1,
                        title: "Пост 1 о JavaScript",
                        body: "текст о JavaScript",
                    },
                    {
                        id: 2,
                        title: "Пост 2 о JavaScript",
                        body: "текст о JavaScript",
                    },
                    {
                        id: 3,
                        title: "Пост 3 о JavaScript",
                        body: "текст о JavaScript",
                    },
                ],
                dialogVisible: false,
            };
        },
        methods: {
            createPost(post) {
                this.posts.push(post);
                this.dialogVisible = false;
            },
            removePost(post) {
                this.posts = this.posts.filter((p) => p.id !== post.id);
            },
            showDialog() {
                this.dialogVisible = true;
            },
        },
    };
</script>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .app {
        padding: 20px;
    }
</style>
<!-- TIMING 1:10:20 -->
