<template>
  <div>
    <h1>Events</h1>

    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, error }) {
    try {
      const { data } = await $axios.get('http://localhost:3001/events');
      return { events: data };
    } catch {
      error({
        statusCode: 503,
        message: 'Unable to fetch events events at this time',
      });
    }
  },
  head() {
    return {
      title: 'Event Listing',
    };
  },
};
</script>
