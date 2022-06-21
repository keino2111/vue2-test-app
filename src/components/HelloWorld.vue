<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <v-app-bar
      color="#6A76AB"
      dark
      shrink-on-scroll
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-3"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <!--左上のメニュー-->
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <!--タイトル-->
      <v-app-bar-title>会社管理画面ホーム</v-app-bar-title>
      <!--右上のアイコン-->
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>

      <!--タイトル下のボタン-->
      <template v-slot:extension>
        <v-row align-with-title>
          <v-btn tile
          color="primary">
          <v-icon left>
              mdi-wrench
          </v-icon>
          マスタ情報管理
          </v-btn>
          <v-btn tile
          color="success">
          <v-icon left>
              mdi-pencil
          </v-icon>
          日時情報管理
          </v-btn>
      </v-row>
      </template>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
