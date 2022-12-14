<template>
    <v-form v-model="valid">
        <v-container>
                <v-text-field
                    v-model="name"
                    :rules="nameRules"
                    :counter="10"
                    label="Name"
                    required
                ></v-text-field>
                <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    :counter="10"
                    label="E-mail"
                    required
                ></v-text-field>
                <v-textarea
                    v-model="pesan"
                    label="Pesan"
                    multi-line
                ></v-textarea>
        </v-container>
    </v-form>

</template>

<script>
    export default {
        data: () => ({
            valid: false,
            name: '',
            nameRules: [
                v => !!v || 'Name is required',
                v => v.length <= 10 || 'Name must be less than 10 characters',
            ],
            email: '',
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+/.test(v) || 'E-mail must be valid',
            ],
        }),
    }
</script>