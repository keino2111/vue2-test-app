<template>
  <v-card
    class="mx-auto"
  >
    <v-system-bar
      color="indigo darken-2"
      dark
    >
      <v-spacer></v-spacer>
    </v-system-bar>

    <v-toolbar
      color="indigo"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>マスタ情報メニュー</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-toolbar>

    <v-container fluid>
      <v-row dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
        >
          <v-card>
              <v-card-title v-text="card.title"></v-card-title>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn>ページへ</v-btn>
              <v-btn icon>
                <v-icon>mdi-share-variant</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    cards: [
      { title: 'テナント会社登録', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 6 },
      { title: 'テナント会社情報編集', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: '会社銀行情報編集', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: 'SC銀行支店登録', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: 'SC銀行支店情報編集', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: '締め回数設定', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 }
    ]
  })
}
</script>
