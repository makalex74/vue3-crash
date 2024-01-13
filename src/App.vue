<template>
    <div>
        <div>
            <button v-on:click="addLike">Like</button>
            <button v-on:click="addDislike">Dislike</button>
        </div>
        <div>Колич-во лайков: <strong>{{ likes }}</strong></div>
        <div>Колич-во дизлайков: <strong>{{ dislikes }}</strong></div>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            likes: 0,
            dislikes: 0,
        }
    },
    methods: {
        addLike(){
            this.likes ++
        },
        addDislike(){
            this.dislikes ++
        }
    }
}
</script>
  
<style>
</style>