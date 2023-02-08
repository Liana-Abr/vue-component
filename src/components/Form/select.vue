<template>
  <div class="custom-select" :tabindex="tabindex" @blur="open = false">
    <div class="selected" :class="{ open: open }" @click="open = !open">
      {{ selected }}
      <i class="fa-solid fa-chevron-down"></i>
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div
          v-for="(option, i) of options"
          :key="i"
          @click="selected = option; open = false;"
      >
        {{ option }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:"select-component",
  props: {
    options: {
      type: Array,
      required: true,
    },
    default: {
      type: String,
      required: false,
      default: null,
    },
    tabindex: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  data() {
    return {
      selected: this.default
          ? this.default
          : this.options.length > 0
              ? this.options[0]
              : null,
      open: false,
    };
  },
};
</script>

<style scoped>
.custom-select {
  margin: 20px;
  position: relative;
  width: 150px;
  text-align: left;
  outline: none;
  line-height: 30px;
}

.custom-select .selected {
  display: flex;
  justify-content: space-between;
  border-radius: 5px;
  border: 2px solid;
  color: black;
  padding-left: 1em;
  cursor: pointer;
  user-select: none;
}
.custom-select .selected i{
  padding: 5px;
}

.custom-select .selected.open {
  border: 2px solid;
  border-radius: 5px 5px 0px 0px;
}

.custom-select .selected:after {
  position: absolute;
  content: "";
  top: 22px;
  right: 1em;
  width: 0;
  height: 0;
  border: 5px solid transparent;
  border-color: #fff transparent transparent transparent;
}

.custom-select .items {
  color: #fff;
  border-radius: 0px 0px 6px 6px;
  overflow: hidden;
  position: absolute;
  background-color: #0084ff;

  left: 0;
  right: 0;
  z-index: 1;
}

.custom-select .items div {
  color: #fff;
  padding-left: 1em;
  cursor: pointer;
  user-select: none;
}

.custom-select .items div:hover {
  background-color: #025baf;
}

.selectHide {
  display: none;
}
</style>
