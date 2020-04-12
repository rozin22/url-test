<template>
  <div class="home">
    <div class="md-layout-item">
      <md-content class="md-elevation-10">
        <div class="input-field">
          <md-field>
            <label>URL Link</label>
            <md-input
              @keyup.enter.native="goLocation"
              ref="url"
              v-model="URL"
            ></md-input>
          </md-field>
        </div>
        <div class="goto">
          <md-button class="md-raised md-primary" @click="goLocation"
            >Go to</md-button
          >
        </div>
      </md-content>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data: () => {
    return {
      URL: ""
    };
  },

  components: {
    // HelloWorld
  },

  methods: {
    goLocation() {
      location.href = "http://" + this.URL;
      this.URL = "";
    }
  }
};
</script>
<style>
.input-field {
  margin: 1rem;
}

.goto {
  padding: 0.2rem 0.2rem;
  display: flex;
}

.md-layout-item {
  margin: 2rem;
}
</style>
