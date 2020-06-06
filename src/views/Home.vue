<template>
  <div class="home">
    <div>
      <ul>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {},
  methods: {
    handleClick(e) {
      console.log(e);
    }
  },
  mounted() {}
};
</script>
<style scoped lang="scss">
.frame {
  height: 500px;
  width: 100%;
}
</style>
