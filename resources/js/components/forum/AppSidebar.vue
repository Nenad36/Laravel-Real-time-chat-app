<template>
    <v-card max-width="450" class="mx-auto">
        <v-toolbar color="cyan" dark dense class="mt-2">
            <v-toolbar-title>Categories</v-toolbar-title>
        </v-toolbar>

        <v-list>
            <v-list-item v-for="category in categories" :key="category.id">
                <v-list-item-content>
                    <v-list-item-title>{{category.name}}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-card>
</template>

<script>
    export default {
        name: "AppSidebar",
        data(){
            return {
                categories:{}
            }
        },
        created(){
            axios.get('/api/category')
                .then(res => this.categories = res.data.data)
        }
    }
</script>

<style scoped>

</style>
