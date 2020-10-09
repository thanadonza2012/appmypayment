<template>

  <v-card
    class="mx-auto"
    max-width="700"

  >
    <v-img
      class="white--text align-end"
      hight="300px"
      src="https://s3.ap-southeast-1.amazonaws.com/www.accrevo.com/blogs/8d15acd0b27626b1fb133df91987a71262b2820d.jpg"
    >
    </v-img>
    <br>
    <br>

<form>
    <v-text-field
      v-model="name"
      :error-messages="nameErrors"
      :counter="10"
      label="Name"
      required
      @input="$v.name.$touch()"
      @blur="$v.name.$touch()"
    ></v-text-field>
    <v-text-field
      v-model="email"
      :error-messages="emailErrors"
      label="E-mail"
      required
      @input="$v.email.$touch()"
      @blur="$v.email.$touch()"
    ></v-text-field>
    <v-text-field
      v-model="name"
      :error-messages="PhonenumberErrors"
      :counter="10"
      label="Phone number"
      required
      @input="$v.name.$touch()"
      @blur="$v.name.$touch()"
    ></v-text-field>
    
    <v-menu
    ref="menu"
    v-model="menu"
    :close-on-content-click="false"
    transition="scale-transition"
    offset-y
    min-width="290px"
  >
    <template v-slot:activator="{ on, attrs }">
      <v-text-field
        v-model="date"
        label="Payment date"
        prepend-icon="mdi-calendar"
        readonly
        v-bind="attrs"
        v-on="on"
      ></v-text-field>
    </template>
    <v-date-picker
      ref="picker"
      v-model="date"
      :max="new Date().toISOString().substr(0, 10)"
      min="1950-01-01"
      @change="save"
    ></v-date-picker>
  </v-menu>


<v-file-input
    label="File input"
    filled
    prepend-icon="mdi-camera"
  ></v-file-input>

    <v-checkbox
      v-model="checkbox"
      :error-messages="checkboxErrors"
      label="Do you agree?"
      required
      @change="$v.checkbox.$touch()"
      @blur="$v.checkbox.$touch()"
    ></v-checkbox>


    <v-btn
      class="mr-4"
      @click="submit"
    >
      submit
    </v-btn>
    <v-btn @click="clear">
      clear
    </v-btn>
  </form>

    
  </v-card>


</template>

<script>
  export default {
    name: 'payment',

    data: () => ({

    }),
  }
</script>
