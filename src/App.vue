<template>
  <v-app id="inspire">
    
    <v-toolbar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      color="primary"
      dark
      app
      fixed
    >
      <v-toolbar-title   class="ml-0 pl-3">
        <span class="hidden-sm-and-down">Teste</span>
      </v-toolbar-title>
      
      <v-btn flat to="/">
        <v-icon>home</v-icon>
      </v-btn>
      <v-btn flat to="instrutores">
        intrutores
      </v-btn>
      <v-spacer></v-spacer>
      
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout justify-center align-center>
          <router-view/>
          
        </v-layout>
      </v-container>
    </v-content>
    
    <v-dialog v-model="dialog" width="800px">
      <v-card>
        <v-card-title
          class="grey lighten-4 py-4 title"
        >
          Create contact
        </v-card-title>
        <v-container grid-list-sm class="pa-4">
                  
                  
        
          
        </v-container>
        
      </v-card>
    </v-dialog>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      dialog: false,
      drawer: null,
      items: [
        { icon: 'contacts', text: 'Contacts' },
        { icon: 'history', text: 'Frequently contacted' },
        { icon: 'content_copy', text: 'Duplicates' },
        {
          icon: 'keyboard_arrow_up',
          'icon-alt': 'keyboard_arrow_down',
          text: 'Labels',
          model: true,
          children: [
            { icon: 'add', text: 'Create label' }
          ]
        },
        {
          icon: 'keyboard_arrow_up',
          'icon-alt': 'keyboard_arrow_down',
          text: 'More',
          model: false,
          children: [
            { text: 'Import' },
            { text: 'Export' },
            { text: 'Print' },
            { text: 'Undo changes' },
            { text: 'Other contacts' }
          ]
        },
        { icon: 'settings', text: 'Settings' },
        { icon: 'chat_bubble', text: 'Send feedback' },
        { icon: 'help', text: 'Help' },
        { icon: 'phonelink', text: 'App downloads' },
        { icon: 'keyboard', text: 'Go to the old version' }
      ]
    }),
    props: {
      source: String
    }
  }
</script>