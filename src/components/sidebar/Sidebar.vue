<template>
    <div class="sidebar">
        <p @click="toHome"> Home </p>
        <p @click="toProfile"> Profile </p>
        <p @click="toSettings"> Settings </p>
        <p @click="logout"> Logout </p>
    </div>
</template>

<script>
export default {
    methods: {
        logout() {
            this.$store.dispatch('logoutSuccess')
            this.$store.dispatch('emptyUser')
            this.$router.push('/')
        },
        toProfile() {
            this.$router.push('/profile')
        },
        toHome() {
            this.$router.push('/home')
        },
        toSettings() {
            this.$router.push('/settings')
        }
    }
}
</script>

<style scoped>

.sidebar {
    flex: 1;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    padding-top: 4rem;
    border-right: solid 5px white;
    background-color: black;
}

p {
    padding: 1rem 0.5rem;
    text-align: center;
    transition-property: all;
    transition-duration: 0.3s;
    cursor: pointer;
    color: white;
}

p:hover {
    border-left: rgb(255, 255, 255) solid 5px;
    background-color: rgba(170, 167, 167, 0.2)
}

@media screen and (max-width: 750px) {

    .sidebar {
        display: none;
    }

}

</style>