<template>
    <v-container grid-list-xs>
        <h1 class="text-center my-5">Meet The Team!</h1>
        <v-divider></v-divider>
        <v-card color="secondary my-5">
            <v-card-title class="text-center">
                Darcy Wells
            </v-card-title>
            <v-card-text>
                <v-row>
                    <v-col cols="12" sm="6" class="d-flex align-center justify-center">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam ex voluptatum reiciendis iste numquam quam minus amet corporis aspernatur possimus, ab quos perspiciatis nihil magni harum quas ullam magnam. Rerum! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Necessitatibus ratione incidunt et, quaerat eos officia assumenda veritatis sapiente, nisi doloremque voluptate sunt ad eaque tempore maiores, dolores quasi totam eveniet!
                    </v-col>
                    <v-col cols="12" sm="6">
                        <v-img max-height="350px" max-width="350px" aspect-ratio="1" class="profile_img" src="Europe_Darcy.jpg"></v-img>
                    </v-col>
                </v-row>
            </v-card-text>
            <v-card-actions>
                <v-btn color="success">Contact Us For a Quote</v-btn>
            </v-card-actions>
        </v-card>
    </v-container>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.profile_img {
    border-radius: 50%;
    border: 1px solid yellow;
    margin-left: 1em;
    margin-right: 1em;
    filter: none;
    transition: filter .5s ease-in-out;
    &:hover {
        filter: grayscale(100%) contrast(120%);
    }
}
</style>