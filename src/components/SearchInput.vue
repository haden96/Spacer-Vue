<template>
  <div class="searchWrapper">
    <input id="search" name="search" :value="value" @input="handleChange" :class="{ dark }"/>
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
};
</script>
<style lang="scss" scoped>
.searchWrapper {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
  input {
    height: 30px;
    border: 0;
    background: none;
    border-bottom: 1px solid black;
  }
}
.dark{
  color: #1e3d4a;
  border-bottom-color:  #1e3d4a;
}

.dark:focus{
  box-shadow: 0 10px 20px -8px rgba(#1e3d4a, .2);
}
</style>
