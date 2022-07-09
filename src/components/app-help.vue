<template>
  <div class="help" id="help">
    <div class="text links">
      <h1>ChatLink</h1>
      <p>
        <strong>Welcome to Chat Link. The best video chat room platform.</strong>
      </p>
      <p>
        Privacy is the driving force behind this application. It uses secure
        technologies like
        <a href="https://yourdomain.com/">WebRTC</a>
        to directly connect between participants. The application that provides the
        web app and mediates the establish
        conversations. No account registration required.
      </p>
    </div>
  </div>
</template>

<style lang="scss">
.help {
  background: rgba(232, 239, 242, 1);
  color: #272727;
  display: block;
  font-family: "IBM Plex Serif", Georgia, serif;
  line-height: 1.5rem;
  padding-bottom: 4rem;

  .text {
    max-width: 40rem !important;
    margin-left: auto !important;
    margin-right: auto !important;
    text-align: left !important;
    padding: 1rem !important;
    padding-top: 4rem !important;
  }

  .text a {
    color: #0088c0 !important;
    text-decoration: none;
  }

  .text a:hover {
    color: #00b5ff !important;
  }

  .text a:active {
    color: #99e2ff !important;
  }
}
</style>

<script>
export default {
  name: "app-help",
  data() {
    return {}
  },
  methods: {},
  async mounted() {},
}
</script>
