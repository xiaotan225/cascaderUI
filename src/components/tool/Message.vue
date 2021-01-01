<template>
  <div class="message" v-if="visible">
    <div class="message-cont">
      <p>{{msg}}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    msg: {
      type: String,
      defulat: ""
    }
  },
  data() {
    return {
      visible: false
    };
  },
  methods: {
    timing() {
      setTimeout(() => {
        this.visible = false;
      }, 2000);
    },
    open() {
      if (this.visible) {
        this.timing();
        return;
      }
      this.visible = true;
    }
  }
};
</script>

<style lang="css">
.message {
  position: absolute;
  left: 50%;
  transform: translate(-50%, 100%);
  animation: cartoon 2s;
}

@keyframes cartoon {
  0% {
    transform: translate(-50%, 100%);
    display: block;
  }
  50% {
    opacity: 0.5;
    display: block;
  }
  100% {
    transform: translate(-50%, 0);
    opacity: 0;
    display: block;
  }
}
.message-cont {
  text-align: center;
  line-height: 35px;
  height: 35px;
  width: 270px;
  background-color: rgb(253, 246, 236);
  border: 1px solid rgb(250, 236, 216);
  border-radius: 2px;
}
.message p {
  color: rgb(230, 162, 60);
}
</style>