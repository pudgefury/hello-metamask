<template>
  <div class="app" id="app">
    <div v-if="!account">
      <button class="primary" @click="connect">
        Connect Wallet To Get Started
      </button>
    </div>
    <div v-else>
      <div>address:{{ account }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {};
  },
  methods: {
    async connect() {
      await this.$store.dispatch("connect", 1);
    },
  },
  async mounted() {
    await this.$store.dispatch("connect");
  },
  computed: {
    account() {
      return this.$store.getters.account;
    },
  },
  components: {},
};
</script>

<style>
</style>
