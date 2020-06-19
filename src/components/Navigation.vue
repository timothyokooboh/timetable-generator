<template>
<!-- This is the navigation component -->
    <div>
        <!-- The app prop makes the navigation bar to be fixed -->
        <v-app-bar app flat color="#fff">

            <v-app-bar-nav-icon @click = "drawer =! drawer" class="hidden-sm-and-up"></v-app-bar-nav-icon>

            <router-link to="/" >
                <a>
                    <v-toolbar-title color="--text">
                        <v-btn text color="#7147B6"> Timetable Generator</v-btn>
                    </v-toolbar-title>
                </a>
            </router-link>

            <v-spacer></v-spacer>

            <router-link to="/" active-class="active" exact>
                <a>
                    <v-btn text color="#7147B6" class="hidden-xs-only"> Home </v-btn>
                </a>
            </router-link>

            <router-link to="/about" active-class="active">
                <a>
                    <v-btn text color="#7147B6" class="hidden-xs-only"> About </v-btn>
                </a>
            </router-link>

            <router-link to="/login" active-class="active">
                <a>
                    <v-btn text color="#7147B6" class="hidden-xs-only"> Login </v-btn>
                </a>
            </router-link>

            <router-link to="/register" active-class="active">
                <a>
                    <v-btn text color="#7147B6" class="hidden-xs-only"> Register </v-btn>
                </a>
            </router-link>



        </v-app-bar>

        <!-- This is the left slidebar menu for mobile screens -->

        <v-navigation-drawer app disable-resize-watcher v-model="drawer" color="#642AD5" class="hidden-sm-and-up">

            <v-list>
                <v-list-item v-for="(route, index) in routes" router :to="route.path" :key="index">

                    <v-btn text color="#fff">
                        <v-list-item-icon>
                            <v-icon>{{route.icon}}</v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            {{route.name}}
                        </v-list-item-content>
                    </v-btn>

                </v-list-item>
            </v-list>
        
        </v-navigation-drawer>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                drawer: false,
                routes: [
                    {
                        name: "Home",
                        path: "/",
                        icon: "mdi-home"
                    },
                    {
                        name: "About",
                        path: "/about",
                        icon: "mdi-logout"
                    },
                    {
                        name: "Login",
                        path: "/login",
                        icon: "mdi-account-plus-outline"
                    },
                    {
                        name: "Register",
                        path: "/register",
                        icon: "mdi-logout"
                    },
                ]
            }
        }
    }
</script>

<style>
   a {
       text-decoration: none;
   } 
   .active {
       border-bottom: 2px solid #6F3CDA;
   }
   .hidden-sm-and-up {
       background-color:var(--secondary-color)
   }
</style>