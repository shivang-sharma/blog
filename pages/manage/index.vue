<template>
  <div class="pt-12">
    <v-row
    justify="center"
    >
      <v-col
        cols="11"
        lg="4"
        md="7"
        sm="8"
        class="pt-12"
      >
        <v-sheet
        elevation="6">
          <v-row
          align="center"
          align-content="center"
          justify="center">
            <v-col
            cols="6"
            sm="4"
            md="3"
            lg="3">
              <i class="fas fa-user icon mt-12"></i>
            </v-col>
          </v-row>
          <v-row
          align="center"
          align-content="center"
          justify="center"
          >
            <v-col
            cols="10"
            sm="8"
            md="6"
            lg="6"
            class="pb-12">
              <form
              class="mb-12">
                <v-text-field
                  @input="$v.email.$touch()"
                  @blur="$v.email.$touch()"
                  v-model="email"
                  :error-messages="emailErrors"
                  label="E-mail"
                  required
                />
                <v-text-field
                  @input="$v.password.$touch()"
                  @blur="$v.password.$touch()"
                  @click:append="show = !show"
                  :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="show ? 'text' : 'password'"
                  v-model="password"
                  :error-messages="passwordErrors"
                  label="Password"
                  class="input-group--focused"
                  required
                />
                <v-row>
                  <v-col
                  cols="3">
                    <v-btn
                      @click="submit"
                      elevation="0"
                      class="mr-4"
                    >
                      login
                    </v-btn>
                  </v-col>
                  <v-col
                  cols="7"
                  class="pl-md-8 pl-sm-12 pl-lg-11 pl-11 ml-10 ml-sm-12 ml-lg-12 ml-md-11 pt-4">
                    <nuxt-link
                      :to="`/sorry`"
                      class="link ml-0">
                      Forgot Password?
                      </nuxt-link>
                  </v-col>
                </v-row>
                </form>
            </v-col>
          </v-row>
        </v-sheet>
      </v-col>
    </v-row>
  </div>
</template>
<style scoped>
.icon{
    font-size: 140px;
    color: lightgrey;
}
.link{
    text-decoration: none;
    color: red;
}
</style>
<script>
import { validationMixin } from 'vuelidate'
import { required, email } from 'vuelidate/lib/validators'

export default {
  mixins: [validationMixin],
  validations: {
    password: { required },
    email: { required, email }
  },
  data: () => ({
    email: '',
    password: '',
    show: false
  }),
  computed: {
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) {
        return errors
      }
      !this.$v.email.email && errors.push('Must be valid e-mail')
      !this.$v.email.required && errors.push('E-mail is required')
      return errors
    },
    passwordErrors () {
      const errors = []
      if (!this.$v.password.$dirty) {
        return errors
      }
      !this.$v.password.required && errors.push('Password is required')
      return errors
    }
  },
  methods: {
    submit () {
      this.$v.$touch()
      if (this.$v.$pending || this.$v.$error) {
        return
      }
      this.$router.push({ path: `/sayhi/admin/` })
    },
    clear () {
      this.$v.$reset()
      this.name = ''
      this.email = ''
      this.select = null
      this.checkbox = false
    }
  }
}
</script>
