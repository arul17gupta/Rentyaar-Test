<template>
  <div class="centered-container">
    <md-content class="md-elevation-3">
      <div class="title">
        <img src="..\assets\Rentyaar.png" />
        <div class="md-title">Rentyaar.com</div>
        <div class="md-body-1">
          The best response to any difficulty is to Figure out a way to make it
          work to your advance
        </div>
      </div>

      <div class="form">
        <md-field>
          <label for="movie">Select college</label>
          <md-select v-model="movie" name="movie" id="movie">
            <md-option value="fight-club">SRM KTR Campus</md-option>
            <md-option value="godfather">SRM Ramapuram Campus</md-option>
            <md-option value="godfather-ii">SRM Gaziyabad Campus</md-option>
            <md-option value="godfather-iii">SRM Sonipath Campus</md-option>
            <md-option value="godfellas">Sample 1</md-option>
            <md-option value="pulp-fiction">Sample 2</md-option>
            <md-option value="scarface">Sample 3</md-option>
          </md-select>
        </md-field>
      </div>

      <div class="actions md-layout md-alignment-center-space-between">
        <!-- <a href="/resetpassword">Reset password</a> -->
        <md-button class="md-raised md-primary" @click="auth">Submit</md-button>
      </div>

      <div class="loading-overlay" v-if="loading">
        <md-progress-spinner
          md-mode="indeterminate"
          :md-stroke="2"
        ></md-progress-spinner>
      </div>
    </md-content>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      loading: false,
      login: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    auth() {
      // your code to login user
      // this is only for example of loading
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
      }, 5000);
    },
  },
};
</script>

<style lang="scss">
.centered-container {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  height: 100vh;
  .title {
    text-align: center;
    margin-bottom: 30px;
    img {
      margin-bottom: 16px;
      max-width: 300px;
    }
  }
  .actions {
    .md-button {
      margin: 0;
    }
  }
  .form {
    margin-bottom: 60px;
  }
  .md-content {
    z-index: 1;
    padding: 40px;
    width: 100%;
    max-width: 400px;
    position: relative;
  }
  .loading-overlay {
    z-index: 10;
    top: 0;
    left: 0;
    right: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    background: rgba(255, 255, 255, 0.9);
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
