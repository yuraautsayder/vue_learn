<template>
    <div class="app">
        <h1>Страница с постами</h1>
        <div class="app_btns">
            <my-button @click="showDialog">Создать пост</my-button>
            <my-select v-model="selectedSort"
            :options="selectOptions"
            />
        </div>

        <my-dialog v-model:show="dialogVisible">
            <PostForm @create="createPost" />
        </my-dialog>
        <div>
            <PostList
                :posts="sortedPosts"
                @remove="removePost"
                v-if="!isPostLoading"
            />
            <div v-else>Идет загрузка...</div>
        </div>
    </div>
</template>

<script>
    import PostForm from "@/components/PostForm";
    import PostList from "@/components/PostList";
    import axios from "axios";
    export default {
        components: {
            PostForm,
            PostList,
        },
        data() {
            return {
                posts: [],
                dialogVisible: false,
                isPostLoading: false,
                selectedSort: "",
                selectOptions: [
                    {
                        value: "title",
                        name: "Название",
                    },
                    {
                        value: "body",
                        name: "Текст",
                    },
                ],
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
            async fetchPosts() {
                try {
                    this.isPostLoading = true;

                    const response = await axios.get(
                        "https://jsonplaceholder.typicode.com/posts?_limit=10"
                    );
                    this.posts = response.data;
                } catch (e) {
                    alert("oshibka");
                } finally {
                    this.isPostLoading = false;
                }
            },
        },
        mounted() {
            this.fetchPosts();
        },
        computed: {
            sortedPosts() {
                return [...this.posts].sort((post1, post2) => {
                    return post1[this.selectedSort]?.localeCompare(post2[this.selectedSort])
                })
            },
        },
        watch: {

        }
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
    .app_btns {
        display: flex;
        justify-content: space-between;
        margin: 15px 0;
    }
</style>
<!-- TIMING 1:39:10 -->
