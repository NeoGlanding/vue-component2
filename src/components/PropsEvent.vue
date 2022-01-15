<template>
    <div @click="getLowerCase" class="">
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
        getLowerCase() {
            this.$emit('get-lower-case', this.username.toLowerCase(), this.username.toUpperCase())
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