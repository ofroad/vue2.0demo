<template>
  <div
    :class="{ drag: 'drag', active: active }"
    @mousedown="down($event)">
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
      active: false,
      offsetX: 0,
      offsetY: 0,
    }
  },
  methods: {
    down(e) {
      this.active = true;
      this.offsetX = (e.pageX - this.$el.offsetLeft);
      this.offsetY = (e.pageY - this.$el.offsetTop);
      addEventListener('mousemove', this.move);
      addEventListener('mouseup', this.up);
    },
    move(e) {
    var  element = this.$el;
      element.style.left = (e.pageX - this.offsetX) + 'px';
      element.style.top = (e.pageY - this.offsetY) + 'px';
    },
    up() {
      this.active = false;
      removeEventListener('mousemove', this.move);
      removeEventListener('mouseup', this.up);
    }
  }
}
</script>

<style>
.drag { position: absolute; top: 8px; left: 8px; width: 180px; height: 80px; background: #eee; }
.drag.active { background: #ddd; }
</style>
