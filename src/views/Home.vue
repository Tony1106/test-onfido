<template>
  <div class="home">
    <button @click="handleClick">Trigger Onfido</button>
    <div id="onfido-mount"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import { init } from "onfido-sdk-ui";
import axios from "axios";
export default {
  name: "Home",
  components: {},
  methods: {
    handleClick(e) {
      this.triggerOnfido();
    },
    triggerOnfido() {
      const url = "https://token-factory.onfido.com/sdk_token";
      // axios
      //   .get(url)
      //   .then(res => console.log(res.data))
      //   .catch(err => console.log(err));
      console.log("cloci");

      init({
        useModal: true,
        isModalOpen: true,
        containerId: "onfido-mount",
        token:
          "eyJhbGciOiJIUzI1NiJ9.eyJwYXlsb2FkIjoiWTIzc1duY0I3RFFUb3o4d2VERXpRWlJMQmtOQzJJUWYvbUxrQXQ5SWF4bkN6SjVGWnJqckVMQ0FhMGZJXG45U25iVXlCWTVIV0M2RHMycW1mNWVMeVZSZz09XG4iLCJ1dWlkIjoiaXdva0ZWZWRHMTgiLCJleHAiOjE1OTE0OTQwOTYsInVybHMiOnsib25maWRvX2FwaV91cmwiOiJodHRwczovL2FwaS5vbmZpZG8uY29tIiwidGVsZXBob255X3VybCI6Imh0dHBzOi8vdGVsZXBob255Lm9uZmlkby5jb20iLCJkZXRlY3RfZG9jdW1lbnRfdXJsIjoiaHR0cHM6Ly9zZGsub25maWRvLmNvbSIsInN5bmNfdXJsIjoiaHR0cHM6Ly9zeW5jLm9uZmlkby5jb20iLCJob3N0ZWRfc2RrX3VybCI6Imh0dHBzOi8vaWQub25maWRvLmNvbSJ9fQ.vrA5SMefsGLYrJyx_bDutPdGsnXwRc8UxHzWf0docrw",
        onComplete: function(data) {
          // callback for when everything is complete
          console.log("everything is complete");
        },
        steps: ["welcome", "document", "face", "complete"]
      });
    }
  }
};
</script>
<style scoped lang="scss">
.frame {
  height: 500px;
  width: 100%;
}
</style>
