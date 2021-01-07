<template>
  <Box class="box" :pose="isVisible ? 'visible' : 'hidden'" />
</template>

<script>
import posed from 'vue-pose';
export default {
  data: () => ({ isVisible: false }),
  components: {
    Box: posed.div({
      visible: { opacity: 1 },
      hidden: { opacity: 0 }
    })
  },
  mounted() {
    setInterval(() => {
      this.isVisible = !this.isVisible;
    }, 1000);
  }
};
</script>

<style>
body {
  display: flex;
  height: 95vh;
  padding: 0;
  margin: 0;
  justify-content: center;
  align-items: center;
}

.box {
  width: 100px;
  height: 100px;
  background: #54E365;
}
</style>
