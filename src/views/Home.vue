<template>
 <div class="home">
  <Toast v-if="showToast" />
  <Todos @badValue="triggerToast" />
  <transition>
   <div v-if="showP"></div>
  </transition>

  <button @click="showP = !showP">toggle</button>
 </div>
</template>

<script>
import { ref } from "vue";
import Toast from "../components/Toast";
import Todos from "../components/Todos";

export default {
 components: { Toast, Todos },
 setup() {
  const showToast = ref(false);
  const showP = ref(false);

  const triggerToast = () => {
   showToast.value = true;
   setTimeout(() => (showToast.value = false), 3000);
  };

  return { showToast, triggerToast, showP };
 },
};
</script>

<style></style>
