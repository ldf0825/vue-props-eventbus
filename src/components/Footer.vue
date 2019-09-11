<template>
  <footer>
    <p>{{copyright}}{{title.name}}</p>
  </footer>
</template>

<script>
export default {
  name: "mr-footer",
  data() {
    return {
      copyright: "Copyright 2019 Vue Footer"
    };
  },
  props: {
    title: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
footer {
  background: lightcoral;
  padding: 6px;
}
p {
  text-align: center;
  color: black;
}
</style>
