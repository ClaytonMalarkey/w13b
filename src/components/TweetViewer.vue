<template>
    <div>
      <!-- Toggle button to switch between list and card view -->
      <button @click="toggleView">{{ listView ? 'Card View' : 'List View' }}</button>
  
      <!-- Render tweets in the selected view -->
      <div v-if="listView" class="list-view">
        <!-- List view layout -->
        <div v-for="tweet in tweets" :key="tweet.id" class="tweet-item">
          <div>{{ tweet.content }}</div>
          <div>By: {{ tweet.user }}</div>
          <div>Created on: {{ tweet.date }}</div>
        </div>
      </div>
      <div v-else class="card-view">
        <!-- Card view layout -->
        <div v-for="tweet in tweets" :key="tweet.id" class="tweet-card">
          <div class="content">{{ tweet.content }}</div>
          <div class="user">By: {{ tweet.user }}</div>
          <div class="date">Created on: {{ tweet.date }}</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        listView: true,
        tweets: [
          { id: 1, content: 'Tweet 1 content', user: 'User 1', date: '2023-10-15' },
          { id: 2, content: 'Tweet 2 content', user: 'User 2', date: '2023-10-16' },
          // Add more tweets as needed
        ],
      };
    },
    methods: {
      toggleView() {
        this.listView = !this.listView;
      },
    },
  };
  </script>
  
  <style scoped>
    /* Add your CSS styles for list and card view here */
  </style>
  