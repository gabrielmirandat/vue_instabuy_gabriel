<template>
  <v-card>
    <v-list three-line>
      <template v-for="item in items">
        <v-list-tile avatar v-bind:key="item.id">

          <v-list-tile-avatar>
            <img v-bind:src="item.imagem">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title v-html="item.nome"></v-list-tile-title>
            <v-list-tile-sub-title v-html="item.marca"></v-list-tile-sub-title>
            <v-list-tile-sub-title v-html="'R$ ' + item.preco"></v-list-tile-sub-title>
          </v-list-tile-content>

        </v-list-tile>

        <v-divider v-if="item.id !== items[items.length-1].id"
                   v-bind:inset="true" v-bind:key="item.nome"></v-divider>

      </template>
    </v-list>
  </v-card>
</template>

<script>
export default {
  name: 'list',
  props: ['items'],
  data () {
    return {
    }
  }
}
</script>
