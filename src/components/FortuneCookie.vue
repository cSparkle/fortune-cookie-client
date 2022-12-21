<template>
    <p>{{ fortune }}</p>
    <button @click.prevent="handleCookieClick">Click me</button>
</template>

<script>

export default {
    name: "fortune-cookie",
    components: {

    },
    data() {
        return {
            fortune: "test"
        }
    },
    methods: {
        handleCookieClick() {
            console.log('cookie clicked')
            // todo fetch data from API
            this.fortune = "clicked"
        }

    }
}

</script>