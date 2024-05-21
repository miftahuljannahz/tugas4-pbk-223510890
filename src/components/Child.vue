<template>
  <div class="child">
    <h2>Ada Pesan Buat Kamu!</h2>
    <GrandchildComponent @message-from-grandchild="handleMessageFromGrandchild" />
    <slot name="additionalContent"></slot>
  </div>
</template>

<script>
import GrandchildComponent from './Child2.vue';

export default {
  components: {
    GrandchildComponent,
  },
  methods: {
    handleMessageFromGrandchild(payload) {
      this.$emit('message-from-child', payload);
    },
  },
};
</script>

<style scoped>
.child {
  padding: 15px;
  background-color: #f0f0f0; 
  border: 1px solid #ccc;
  border-radius: 8px; 
  margin-top: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); 
}

.grandchild {
  padding: 10px;
  background-color: #EEF7FF;
  border: 1px solid #ccc; 
  border-radius: 5px;
  margin-top: 10px;
}

.grandchild button {
  padding: 8px 16px; 
  border: none;
  border-radius: 5px;
  background-color: #007bff;
  color: white;
  cursor: pointer;
  margin-right: 10px;
  transition: background-color 0.3s ease;
}

.grandchild button:hover {
  background-color: #0056b3;
}
</style>
