<template>
  <v-layout row>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
        <v-toolbar class="teal lighten-3 white--text" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>Manage</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>more_vert</v-icon>
          </v-btn>
        </v-toolbar>
        <v-list class="teal darken-4">
          <template v-for="item in items">
            <v-list-tile v-if="item.action" v-bind:key="item.title" @click="">
              <v-list-tile-action>
                <v-icon dark>{{ item.action }}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content class="white--text">
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-divider v-else-if="item.divider" dark></v-divider>
            <v-subheader v-else-if="item.header" v-text="item.header" class="grey--text text--lighten-4"></v-subheader>
          </template>
        </v-list>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            action: 'move_to_inbox',
            title: 'Inbox'
          },
          {
            action: 'send',
            title: 'Sent'
          },
          {
            action: 'delete',
            title: 'Trash',
          },
          {
            action: 'report',
            title: 'Spam'
          },
          { divider: true },
          { header: 'Labels' },
          {
            action: 'label',
            title: 'Family'
          },
          {
            action: 'label',
            title: 'Friends'
          },
          {
            action: 'label',
            title: 'Work',
          }
        ]
      }
    }
  }
</script>
