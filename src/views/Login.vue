<template>
    <div class="register">
        <v-container>

            <v-card>
              
                <v-card-title>
                    <v-btn text x-large color="#7147B6"> Welcome Back</v-btn>
                </v-card-title>

                <v-form ref="form" @submit="submit" class="mx-5">
                    <v-text-field
                        v-model = "email"
                        label = "Email Address"
                        type = "email"
                        append-icon = "mdi-email"
                        outlined
                        shaped 
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

                    <v-btn type="submit"  :loading ="loadingContent" width = "100%" rounded color = "#6b37d8" class = "white--text mb-5">Log In</v-btn>

                    <div class="flex-container pb-5">
                        <div>
                            <v-btn text small color="#7147B6"> Forgot Password? </v-btn>
                        </div>
                        <div>
                            <v-btn text small color="#7147B6"> 
                                <router-link to="/register"> Create Account </router-link>
                            </v-btn>
                        </div>
                    </div>

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
    .flex-container {
        display: flex;
        justify-content: space-between;
    }

   a {
     color: #7147B6  
   }
</style>