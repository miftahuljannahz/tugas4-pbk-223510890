<template>
  <div class="grandchild">
    <h3>Tekan Submit!!</h3>
    <button @click="sendMessageToParent">Submit</button>
    <button class="cancel" @click="cancelSubmit">Cancel</button>
  </div>
</template>

<script>
export default {
  methods: {
    sendMessageToParent() {
      this.$emit('message-from-grandchild', 'Jalani saja, nanti juga sampai. Segala hal yang kita lewati adalah sebuah perjalanan,jadi tetaplah berusaha sampai di kilometer selanjutnya.');
    },
    cancelSubmit() {
      console.log("Submit dibatalkan!");
      this.$emit('message-from-grandchild', ''); 
    },
  },
};
</script>

<style scoped>
.grandchild {
  padding: 20px;
  background: linear-gradient(135deg, #f0f0f0 25%, #ffffff 100%);
  border: 1px solid #ccc;
  border-radius: 10px;
  margin-top: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

button {
  padding: 12px 24px; 
  border: none;
  border-radius: 25px;
  background-color: #007bff;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
  margin: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

button:hover {
  background-color: #0056b3;
  transform: translateY(-2px);
}

button:active {
  background-color: #003d99;
  transform: translateY(0);
}

button.cancel {
  background-color: #dc3545;
}

button.cancel:hover {
  background-color: #c82333;
  transform: translateY(-2px);
}

button.cancel:active {
  background-color: #a71d2a;
  transform: translateY(0);
}
</style>
