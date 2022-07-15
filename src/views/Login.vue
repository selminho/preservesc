<template>
  <v-container fill-heigth fluid text center>
    <v-container>
        <v-row>
            <v-col 
              class="black--text text-center mx-auto pb-4" 
              cols="1" 
              sm="4" 
              offset="4"
            ><h1 class="h1">PRESERVE SC - Login</h1></v-col
            >
        </v-row>
        <v-row class="elevation-3 mx-auto" >
            <v-col cols="auto">
                <v-img max-height="150" max-width="250" scr="@/assets/images/logo1preserve.png">

                </v-img>
            </v-col>
            <v-col>
                <v-form>
                    <v-text-field label="E-mail" v-model="user.email"></v-text-field>
                    <v-text-field 
                        label="Senha" 
                        v-model="user.password"
                        :type="show ? 'text' : 'password'"
                        :append-icon="show ? 'mdi-shark' : 'mdi-shark-off'"
                        @click:append="show = !show"
                    ></v-text-field>
                    <v-btn color="green" @click="login">Entrar</v-btn>
                    <v-btn class="ml-2" color="blue" @click="reset">Limpar</v-btn>
                </v-form>
            </v-col>
        </v-row>
    </v-container>
    <v-snackbar 
     color="red"
     v-model="errorLogin" 
     danger multline
     timeout="2000"
     >
     Usuário ou senha inválidos
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
    data() {
        return {
            user: {},
            show: false,
            errorLogin: false,
        };
    },
    methods: {
        reset() {
            this.user = {};
        },
        login() {
            if(this.user.email === 'henry' && this.user.password === 'henry') {
                this.$router.push({ name: "Home" });
            } else {
                this.errorLogin = true;
            }
        },
    },
};
</script>

<style>

</style>