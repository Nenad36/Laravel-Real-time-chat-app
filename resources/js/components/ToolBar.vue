<template>
    <nav>
        <v-toolbar color="deep-purple accent-4" dense dark>
            <v-toolbar-title>
                <router-link class="white--text" to="/">
                    <span class="font-weight-light">Forum</span>
                    <span>App</span>
                </router-link>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <app-notification v-if="loggedIn"></app-notification>

            <router-link
                v-for="item in items"
                :key="item.title"
                :to="item.to"
                v-if="item.show">
                <v-btn text>{{item.title}}</v-btn>
            </router-link>

        </v-toolbar>
    </nav>
</template>

<script>
import AppNotification from "./AppNotification";

   export default {
        name: "ToolBar",
       components: { AppNotification },
       data() {
           return {
               loggedIn: User.loggedIn(),
               items: [
                   { title: "Forum", to: "/forum", show: true },
                   { title: "Ask Question", to: "/ask", show: User.loggedIn() },
                   { title: "Category", to: "/category", show: User.admin() },
                   { title: "Login", to: "/login", show: !User.loggedIn() },
                   { title: "Logout", to: "/logout", show: User.loggedIn() }
               ]
           };
       },
       created() {
           EventBus.$on("logout", () => {
               User.logout();
           });
       }
    }
</script>

<style lang="scss" scoped>
    .md-toolbar + .md-toolbar {
        margin-top: 16px;
    }
</style>
