<template>
    <div class="register">
        <v-container>
            <v-card flat>
              
                <v-card-title>
                    <v-btn text color="#7147B6" class="title"> CREATE ACCOUNT</v-btn>
                </v-card-title>

                <v-form ref="form" @submit="submit" class="mx-5 ">

                <!-- I hope to include social login to enable users sign up with their gmail account -->

                    <v-btn color="#6b37d8" class="white--text" rounded width="100%">
                        <v-icon left>mdi-google</v-icon>
                        <span> Sign UP With Google </span>
                    </v-btn>

                    <v-btn text color="#7147B6" class="my-4 title" left> OR</v-btn>

                    <v-text-field
                        v-model = "email"
                        label = "Email Address"
                        type = "email"
                        append-icon = "mdi-email"
                        outlined
                        shaped
                        autocomplete                       
                        :rules = "emailRules"
                    >
                    <!-- The "rules" prop is an array of functions used for validating users input -->
                    </v-text-field>

                    <v-text-field
                        v-model = "password"
                        label = "Password"
                        type = "password"
                        append-icon = "mdi-key"
                        outlined
                        shaped
                        :rules = "passwordRules"
                    >
                    <!-- The "rules" prop is an array of functions used for validating users input -->
                    </v-text-field>

                    <v-btn type="submit"  :loading ="loadingContent" width = "100%" rounded color = "#6b37d8" class = "white--text mb-5">Sign Up</v-btn>
                    <!-- The "loading" prop is used to add a button loader -->

                    <v-btn text small color="#7147B6" class="my-3">
                        <router-link to="/login" > Have an account? Log In</router-link>
                    </v-btn>
                    
                </v-form>
            </v-card>
        </v-container>
    </div>
</template>

<script>
export default {
    name: 'Home',
    data() {
        return {
            email: "",
            password: "",
            loadingContent: false,
            emailRules: [
                v => !!v || "Email is required",
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
            ],
            passwordRules: [
                v => !!v || "Password is required",
                v => v.length >=8 || "Password must be at least 8 characters"
            ]
        }
    },
    methods: {
       submit(e) {
           if(this.$refs.form.validate()) {
               this.loadingContent = true
               return true
           }
           e.preventDefault()
       }
    }
}
</script>

<style scoped>
   a {
     color: #7147B6  
   }
</style>