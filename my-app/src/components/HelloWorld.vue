<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-contact-mail</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Contact</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="indigo"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container
        class="fill-height"
        fluid
      >
      
   <form>
    <v-text-field
      v-model="id"
      :error-messages="idErrors"
      :counter="100"
      label="User ID"
      required
      @input="$v.id.$touch()"
      @blur="$v.id.$touch()"
    ></v-text-field>
    <v-select
      v-model="selecttype"
      :items="Type"
      :error-messages="selectErrors"
      label="Type"
      required
      @change="$v.selecttype.$touch()"
      @blur="$v.selecttype.$touch()"
    ></v-select>
    <v-select
      v-model="selectorg"
      :items="OrgID"
      :error-messages="selectErrors"
      label="Org ID"
      required
      @change="$v.selectorg.$touch()"
      @blur="$v.selectorg.$touch()"
    ></v-select>
    <v-text-field
      v-model="code"
      :error-messages="emailErrors"
      label="Product Code"
      required
      @input="$v.code.$touch()"
      @blur="$v.code.$touch()"
    ></v-text-field>
     <v-text-field
      v-model="billing"
      :error-messages="emailErrors"
      label="Billing Number"
      required
      @input="$v.billing.$touch()"
      @blur="$v.billing.$touch()"
    ></v-text-field>
    <v-text-field
      v-model="tanggal"
      :error-messages="emailErrors"
      label="Tanggal"
      required
      @input="$v.tanggal.$touch()"
      @blur="$v.tanggal.$touch()"
    ></v-text-field>
    <v-checkbox
      v-model="checkbox"
      :error-messages="checkboxErrors"
      label="Do you agree?"
      required
      @change="$v.checkbox.$touch()"
      @blur="$v.checkbox.$touch()"
    ></v-checkbox>

    <v-btn class="mr-4" @click="submit">submit</v-btn>
    <v-btn @click="clear">clear</v-btn>
  </form>
      </v-container>
    </v-content>
    <v-footer
      color="indigo"
      app
    >
      <span class="white--text">&copy; 2019</span>
    </v-footer>
  </v-app>
</template>


<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
    }),
  }
</script>