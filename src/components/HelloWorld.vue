<template>
    <div class="hello">
        <button :disabled="isAuthenticated" @click="$adal.login()">Sign In</button>
        <button :disabled="!isAuthenticated" @click="$adal.logout()">Sign Out</button>
        <br>
        <h2 v-if="!isAuthenticated">Please sign in</h2>
        <h1 v-if="isAuthenticated">Hello, {{ isAuthenticated.profile.name }}!!</h1>
    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class HelloWorld extends Vue {
        @Prop() private msg!: string;
    }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    button {
        margin: 10px;
        padding: 5px 15px;
    }
</style>
