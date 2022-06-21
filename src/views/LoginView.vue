<template>
<div id="app">
  <v-app>
    <v-card class="login">
      <v-card-title class="main">管理画面ログイン</v-card-title>
      <v-card-text>
        <v-form ref="loginForm" v-model="valid">
        <v-text-field v-model="companyCode"
          label="施設企業コード"
          counter="4"
          :rules="[required, companyCodeRule]"
          type="number"
          outlined
          clearable
          prepend-icon="mdi-account-box"
        >
        </v-text-field>
        <v-select v-model="selectUserType"
          label="ユーザタイプ"
          :items="userTypes"
          :rules="[required]"
          item-text="type"
          item-value="code"
          outlined
          prepend-icon="mdi-account-question"
        ></v-select>
        <v-text-field v-model="scCode" v-show="true"
          label="施設コード"
          counter="4"
          :rules="[required, scCodeRule]"
          type="number"
          outlined
          clearable
          prepend-icon="mdi-account-box"
          >
        </v-text-field>
        <v-text-field v-model="userName"
          label="ユーザ名"
          counter="20"
          :rules="[required, userNameRule]"
          outlined
          clearable
          prepend-icon="mdi-account-circle"
        >
        </v-text-field>
        <v-text-field v-model="password"
          label="パスワード"
          counter="36"
          :rules="[required, passwordRule]"
          v-bind:type="showPassword ? 'text' : 'password'"
          @click:append="showPassword=!showPassword"
          outlined
          clearable
          prepend-icon="mdi-lock"
          v-bind:append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
        >
        </v-text-field>
        </v-form>
      </v-card-text>
      <v-divider></v-divider>
      <v-card-actions>
        <v-btn v-on:click="submit" :disabled="!valid" class="mr-4"
          color="green"
        >ログイン</v-btn>
        <v-btn @click="reset" class="mr-4"
          color="red"
        >取り消し</v-btn>
        <v-btn class="mr-4" color="orange">
          パスワードをお忘れの場合
        </v-btn>
        <span v-if="success">送信成功！</span>
      </v-card-actions>
    </v-card>
  </v-app>
</div>
</template>

<script>
export default {
  data () {
    return {
      companyCode: '',
      scCode: '',
      selectUserType: 1,
      userName: '',
      text3: '',
      success: false,
      valid: false,
      showPassword: false,

      required: (v) => !!(v) || '必ず入力してください',
      companyCodeRule: [(v) => (v).length <= 4 || '企業コードは4文字以内です'],
      scCodeRule: (v) => (v).length <= 4 || '施設コードは4文字以内です',
      userNameRule: (v) => (v).length <= 20 || 'ユーザ名は20文字以内です',
      passwordRule: (v) => (v).length <= 36 || 'パスワードは36文字以内です',

      userTypes: [{ type: '施設ユーザ', code: 'sc_user' }, { type: '企業ユーザ', code: 'company_user' },
        { type: '管理者', code: 'admin' }]
    }
  },
  methods: {
    submit () {
      this.success = true
    },
    reset () {
      this.$refs.loginForm.reset()
    }
  }
}
</script>

<style scoped>
  v-card.login {
    margin: 1em auto;
    width: 50%;
  }

  v-card-title.main {
    text-align: center;
    margin: 0 0;
  }
</style>
