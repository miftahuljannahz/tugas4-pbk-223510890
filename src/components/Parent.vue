<template>
  <div class="parent">
    <h1>Ini adalah tugas 4 saya.</h1>
    <p>{{ message }}</p>
    <ChildComponent @message-from-child="handleMessageFromChild">
      <template v-slot:additionalContent>
        <p class="additional-content">© Miftahul Jannah - 223510890 | 4D </p>
      </template>
    </ChildComponent>
  </div>
</template>

<script>
import ChildComponent from './Child.vue';

export default {
  components: {
    ChildComponent,
  },
  data() {
    return {
      message: 'Tidak Ada Pesan Yang Masuk.',
    };
  },
  methods: {
    handleMessageFromChild(payload) {
      this.message = payload;
    },
  },
};
</script>

<style scoped>
.parent {
  padding: 20px;
  background-color: #f0f0f0; 
  border: 1px solid #ccc;
  border-radius: 10px; 
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
  text-align: center;
}

h1 {
  color: #000000; 
  margin-bottom: 20px; 
}

p {
  color: #666; 
  margin-bottom: 20px; 
}

.additional-content {
  color: #888; 
}
</style>
