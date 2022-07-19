<template>
  <b-row class="vh-100 vw-100 row-login">
    <b-col sm="5" class="d-flex justify-content-center align-items-center left-login">
        <div class="col-8">
            <h2 class="text-center mb-5 title-login"><font color="white">FAÇA SEU LOGIN!</font></h2>

            <b-form>
                <b-form-group
                    label-for="email"
                    >
                    <label class="d-flex justify-content-between">
                        <h6>
                            <font color="white" face="Andale Mono, monospace">E-mail</font>
                        </h6>
                    </label>
                      <b-form-input
                        id="email"
                        type="email"
                        placeholder="E-mail"
                        v-model="form.email"
                        >
                      </b-form-input>
                </b-form-group>

                <b-form-group
                    label-for="password"
                    >
                    <label class="d-flex justify-content-between">
                        <h6>
                            <font color="white" face="Andale Mono, monospace">
                                Senha
                            </font>
                        </h6>
                        <small><a href="#" ><font color="white">Esqueceu sua senha?</font></a></small>
                    </label>

                      <b-form-input
                        id="password"
                        type="password"
                        placeholder="Digite sua senha"
                        v-model="form.password"
                        >
                      </b-form-input>
                </b-form-group>

                <b-button
                 type="button"
                 variant="outline-light"
                 block
                 @click="login"
                 >
                   <i class="fas fa-sign-in-alt"></i> Entrar
                </b-button>

                <hr>

                <b-button
                 type="button"
                 variant="outline-success"
                 block
                 @click="register"
                 >
                   <i class="fas fa-user-plus"></i> Fazer meu cadastro
                </b-button>

            </b-form>
        </div>
    </b-col>
    <b-col sm="7" class="d-flex justify-content-center align-items-center">
        <img src="@/assets/images/preserve.png" class="img-login">
    </b-col>
  </b-row>
</template>

<script>
export default {
    data() {
        return {
            form: {
                email: "",
                password: ""
            }
        }
    },

    

    }

</script>

<style>

*,
*::after,
*::before {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-decoration: none;
}

.row-login {
    margin-left: 0,
}

.left-login {
    background-color: black;
}

.title-login {
    font-weight: bold;
    font-family: 'Courier New', monospace;
}

.img-login {
    width: 600px;
    height: 600px;
}

</style>