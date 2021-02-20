<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app
    :mobile-breakpoint="768"
    >
      <v-img
      class="pa-4"
      src="./assets/purpleMountain.jpg"

      max-height="160"
      max-width="250"

      >
          <v-avatar 
          
          size="70"
          
          >
      <img
        src="./assets/jakobYaro.png"
        alt="John"
      >
    </v-avatar>
      <div class="white--text text-subtitle-1 " >Jakob Yaro</div>
      <div class="white--text text-subtitle-2 " >javautvecklare</div>


      
      </v-img>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title> {{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="primary"
      dark
      src="./assets/astrobg.jpg"
      prominent
      :height="$route.path ==='/' ? '250': '150' " 
    >





      <v-container class="pa-0">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer">
          </v-app-bar-nav-icon>
          <v-spacer></v-spacer>
          <search />
        </v-row>

        <v-row>
          <v-toolbar-title class="ml-4 text-h3 ">{{$store.state.apptitle}} </v-toolbar-title>
        </v-row>
        <v-row class="text-h8">
          <live-date-time/>

        </v-row>
        <v-row
        v-if="$route.path ==='/'"
        >
    <field-add-task/>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main>
      <!--  -->
      <router-view> </router-view>
    </v-main>
    <snackbar />
  </v-app>
</template>

<script>
import SnackBar from "../src/components/Shared/SnackBar";
import Search from "../src/components/Tools/Serach";
import LiveDateTime from '../src/components/Tools/LiveDateTime'
import FieldAddTask from '../src/components/FieldAddTask.vue'



export default {
  data: () => ({
    drawer: false,
    items: [
      { title: "Todo-App", icon: "mdi-format-list-checks", to: "/" },
      { title: "About", icon: "mdi-help-box", to: "/about" },
    ],
  }),
  components: {
    snackbar: SnackBar,
    search: Search,
    'live-date-time': LiveDateTime,
    'field-add-task': FieldAddTask,

  },
  mounted() {
    this.$store.dispatch('getTasks')
  }

};
</script>

<style lang="sass" >
  .header-container
    max-width: none
</style>