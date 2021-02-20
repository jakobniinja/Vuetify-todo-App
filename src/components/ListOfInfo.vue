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
        { text: 'Ec Utbildningar', icon: 'mdi-clock', link:'https://ecutbildning.se/utbildningar/javautvecklare/stockholm/',id: 0 },
        { text: 'My Resumé', icon: 'mdi-poll', link:'https://www.docdroid.net/lU5j2uo/cv-jakobyaro-1-pdf',id: 1 },
        { text: 'Github', icon: 'mdi-palette', link:'https://github.com/jakeHacker99',id: 2 },
        { text: 'Contact', icon: 'mdi-android-messages', link:'https://wa.me/+46793351364?text=tja%20jakob%20jag%20gillade%20din%20VuetifoTodo-app%20;)',id: 2 }
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