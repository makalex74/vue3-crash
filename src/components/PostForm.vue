<template>
    <form @submit.prevent>
        <h4>Создание поста</h4>
        <input v-model="post.title" class="input" type="text" placeholder="Название">
        <input v-model="post.body" @input="post.body = $event.target.value" class="input" type="text" placeholder="Описание">
        <my-button style="align-self: flex-end; margin-top: 15px;" @click="createPost">Создать</my-button>
    </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
    components: {'my-button': MyButton},
    data() {
        return {
            post: {
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post)
            this.post = {
                title: '',
                body: ''
            }
        }
    }

}
</script>

<style scoped>
form {
    display: flex;
    flex-direction: column;
}

.input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}

</style>