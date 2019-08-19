<template>
   <v-app>
       <v-app-bar app dense>
         <v-toolbar-title>Admin</v-toolbar-title>
         <v-spacer></v-spacer>
         <v-toolbar-items class="hidden-sm-and-down">
           <v-btn  text>Справочники</v-btn>
           <v-btn  text>Конвертации</v-btn>
           <v-btn  text>Рецепты</v-btn>
           <v-btn icon>
             <v-icon>
               logout
             </v-icon>
           </v-btn>
         </v-toolbar-items>
         <v-menu offset-y>
           <template v-slot:activator="{ on }">
             <v-app-bar-nav-icon v-on="on" class="hidden-md-and-up">
             </v-app-bar-nav-icon>
           </template>
           <v-list>
             <v-list-item>
               <v-btn  text>Справочники</v-btn>
             </v-list-item>
             <v-list-item>
               <v-list-item-title>
                 <v-btn  text>Конвертации</v-btn>
               </v-list-item-title>
             </v-list-item>
             <v-list-item>
               <v-list-item-title>
                 <v-btn  text>Рецепты</v-btn>
               </v-list-item-title>
             </v-list-item>
             <v-list-item>
               <v-btn icon>
                 <v-icon>
                   logout
                 </v-icon>
               </v-btn>
             </v-list-item>
           </v-list>
         </v-menu>
       </v-app-bar>
      <v-content v-resize="onResize" >
        <v-container fluid class="pa-0">
          <v-row no-gutters>
            <v-col cols="1">
              <v-row>
                  <v-btn block :height="parentHeight">
                  Long
                </v-btn>
              </v-row>
            </v-col>
            <v-col>
              <v-row>
                <v-btn rounded block :height="0.5 * parentHeight">
                  Alpha
                </v-btn>
                <v-btn rounded block :height="0.25 * parentHeight">
                  Bravo
                </v-btn>
                <v-btn rounded block :height="0.25 * parentHeight">
                  Charlie
                </v-btn>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-content>
      <v-footer app color="indigo">
        <span class="white--text">&copy; 2019</span>
      </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'app',
  components: {
  },
  data(){
    return{
      parentHeight:0,
    }
  },
  mounted(){
    this.onResize();
  },
  methods:{
    onResize(){
      this.parentHeight=window.innerHeight - this.$vuetify.application.top - this.$vuetify.application.footer;
    }
  }


}
</script>

<style>
  @media print {
    nav, aside {
      display: none !important;
    }
  }
</style>
