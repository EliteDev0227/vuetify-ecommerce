<template>
  <div style="width:100%; height: 50px; background-color:#10504f; position:absolute; top:50px; z-index:1">
    <v-btn
      min-height="48"
      min-width="40"
      text
      class="float-left"
      style="padding: 0 !important"
    >
      <v-icon
        size="20"
      >
        mdi-account-multiple-plus
      </v-icon>
    </v-btn>
    <v-img
      class="float-left"
      max-height="48"
      max-width="100"
      style="margin-top: 1px; width:auto; height: auto;"
      :src="require('@/assets/logo.png')"
    />
    <v-btn
      v-for="(item, i) in items"
      :key="i"
      class="float-right"
      min-height="48"
      min-width="40"
      text
      :to="item.to"
      style="padding: 0 !important"
    >
      <v-icon
        size="20"
        v-text="item.icon"
      />
    </v-btn>
  </div>
</template>

<script>
  export default {
    name: 'PagesTopBar',

    data: () => ({
      items: [
        {
          icon: 'mdi-view-dashboard',
          text: 'Dashboard',
          to: '/',
        },
        {
          icon: 'mdi-currency-usd',
          text: 'Pricing',
          to: '/pages/pricing',
        },
        {
          icon: 'mdi-account-multiple-plus',
          text: 'Register',
          to: '/pages/register',
        },
      ],
      titles: {
        '/pages/lock': 'Lock Page',
        '/pages/login': 'Login Page',
        '/pages/pricing': 'Pricing Page',
        '/pages/register': 'Register Page',
      },
    }),

    computed: {
      title () {
        return this.titles[this.$route.path]
      },
    },
  }
</script>
