<template>
    <v-card class="mt-2">
        <div>
            <v-card-title>
                <router-link :to="data.path">
                    {{ data.title }}
                </router-link>
            </v-card-title>

            <v-card-subtitle class="pb-0">
             {{ data.user }} said {{ data.created_at }}
            </v-card-subtitle>
        </div>
        <v-card-text class="text--primary">
            <div>{{ data.body }}</div>
        </v-card-text>
    </v-card>
</template>

<script>
    export default {
        name: "Question",
        props:['data']
    }
</script>

<style scoped>

</style>
