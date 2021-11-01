<template>
  <div>
    <h1>Following {{ username }}</h1>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: `Dashboard ${this.username}`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: `Info about ${this.username}`,
        },
      ],
    };
  },
  computed: {
    username() {
      return this.$route.params.username;
    },
  },
};
</script>
