<template>
    <div @click="deleteUsername" class="">
        <p :class="{odd: username.length % 2 !== 0}">{{ username }}</p>
    </div>
</template>

<script>
export default {
    props: {
        username: {
            type: String
        }
    },
    methods: {
        deleteUsername() {
            this.$emit('delete-friends', this.username)
        }
    }
}
</script>

<style scoped>
    div {
        background-color: aqua;
    }

    .odd {
        color: red;
    }
</style>