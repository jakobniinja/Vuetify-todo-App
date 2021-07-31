    <template>
  <v-card
    class="mx-auto"
    max-width="300"
    tile
  >
    <v-list flat>
      <v-subheader></v-subheader>
      <v-list-item-group
        v-model="selectedItem"
        color="purple darken-1"
      >
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
          @click="handleClick(index)"

        >
        
          <v-list-item-icon>
            <button
              class="hover-me"

            >
            <v-icon v-text="item.icon"></v-icon>
            </button>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>

</template>


<script>
export default {
    data:() => ({
      selectedItem: 1,
      items: [
        { text: 'My Cv', icon: 'mdi-poll', link:'https://www.docdroid.net/d7pJFCi/cv-javautvecklare-docx',id: 1 },
        { text: 'Linkedin', icon: 'mdi-linkedin', link:'https://linkedin.com/in/jakob-yaro-178546205',id: 2 },
        { text: 'Github', icon: ' mdi-github', link:'https://github.com/jakeHacker99',id: 3 },
        { text: 'Contact', icon: 'mdi-android-messages', link:'https://wa.me/+46793351364?text=tja%20jakob%20jag%20gillade%20din%20VuetifoTodo-app%20;)',id: 4 }
      ],
      

    }),
    methods:{
    handleClick(index) {
      console.log(this.items[index].link)
      
        window.open(this.items[index].link, "_blank");    
    },
  },

    
}
</script>

<style scoped>
button{
  cursor: pointer;
}


</style>
