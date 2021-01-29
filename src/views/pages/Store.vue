<template>
  <v-container
    id="pricing"
    class="fill-height justify-center"
    tag="section"
  >
    <carousel
      center-mode="true"
      scroll-per-page="false"
      per-page="1"
    >
      <slide>
        <v-img
          max-height="200px"
          style="width:auto; height:auto"
          :src="require('@/assets/logo.png')"
        />
      </slide>
      <slide>
        <v-img
          max-height="200px"
          style="width:auto; height:auto"
          :src="require('@/assets/logo.png')"
        />
      </slide>
      <slide>
        <v-img
          max-height="200px"
          style="width:auto; height:auto"
          :src="require('@/assets/logo.png')"
        />
      </slide>
    </carousel>
    <v-row
      align="center"
      class="text-center"
      justify="center"
    >
      <v-col
        class="mb-10"
        cols="12"
      >
        <pages-heading class="mb-12">
          Shop new arrivals
        </pages-heading>

        <div class="display-1 font-weight-light grey--text text--lighten-2">
          You have Free Unlimited Updates and Premium Support on&nbsp;<br class="hidden-sm-and-down">each package.
        </div>
      </v-col>

      <template v-for="(plan, i) in plans">
        <v-col
          :key="i"
          class="d-flex"
          cols="12"
          sm="6"
          md="3"
        >
          <pages-plan-card :plan="plan" />
        </v-col>

        <v-col
          v-if="(i === 1 && $vuetify.breakpoint.smAndDown) && i + 1 !== plans.length"
          :key="`divider-${i}`"
          class="pa-6"
          cols="12"
        >
          <v-divider />
        </v-col>
      </template>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Store',

    components: {
      PagesHeading: () => import('./components/Heading'),
      PagesPlanCard: () => import('./components/PlanCard'),
    },

    data: () => ({
      plans: [
        {
          heading: 'Freelancer',
          icon: 'mdi-sofa',
          title: 'Free',
          text: 'This is good if your company size is between 2 and 10 Persons.',
        },
        {
          best: true,
          heading: 'Small Company',
          icon: 'mdi-home',
          title: '29$',
          text: 'This is good if your company size is between 2 and 10 Persons.',
        },
        {
          heading: 'Medium Company',
          icon: 'mdi-domain',
          title: '69$',
          text: 'This is good if your company size is between 11 and 99 Persons.',
        },
        {
          heading: 'Extra Pack',
          icon: 'mdi-bank',
          title: '159$',
          text: 'This is good if your company size is 99+ or greater Persons.',
        },
      ],
      items: [
        {
          icon: 'mdi-account-multiple-plus',
          text: 'Register',
          to: '/pages/register',
        },
        {
          icon: 'mdi-fingerprint',
          text: 'Login',
          to: '/pages/login',
        },
        {
          icon: 'mdi-lock-open-outline',
          text: 'Lock',
          to: '/pages/lock',
        },
      ],
    }),
  }
</script>
