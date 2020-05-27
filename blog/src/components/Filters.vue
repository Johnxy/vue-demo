<template>
  <div class="hello">
    <span>时间：{{ date | dateFormat }}</span>
    <span v-pre> {{ preText }} </span>
    <span v-html="preText"> </span>
  </div>
</template>

<script>
export default {
  name: 'Filters',
  props: {
    date: String
  },
  filters: {
    dateFormat(value) {
      let date = new Date(value);
      return `${date.getFullYear()}-${date.getMonth() + 1}-${date.getDate()}`;
    },
  },
  data() {
    return {
      preText: '<div>过滤器</div>'
    };
  }
}
</script>
