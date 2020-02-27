<template>
    <v-footer
       color="primary lighten-1"
       padless
       inset app
    >
    <v-row
       justify="center pl-0"
       no-gutters
    >
    <v-col
       class="primary lighten-2 py-4 text-center white--text"
       cols="12"
    >
        {{ new Date().getFullYear() }} — <strong>Forum App</strong>
    </v-col>
    </v-row>
   </v-footer>
</template>
<!--<template>-->
<!--    <v-footer class="justify-center pl-0" inset app>-->
<!--        <span>&copy; 2018</span>-->
<!--    </v-footer>-->
<!--</template>-->
<script>
    export default {
        name: "AppFooter"

        }
</script>

<style scoped>

</style>
