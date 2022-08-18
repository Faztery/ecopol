<template>
  <div class="bill">
    <h1>AQUI VA EL CONTENIDO</h1>

    <button class="btn bg-indigo-500 hover:bg-indigo-600 text-white" aria-controls="feedback-modal"
      @click.stop="feedbackModalOpen = true">Send Feedback</button>
    <ModalBasic id="feedback-modal" :modalOpen="feedbackModalOpen" @close-modal="feedbackModalOpen = false"
      title="Send Feedback">


  </div>
</template>
<script>
import { ref } from 'vue';
import ModalBasic from '../components/ModalBasic';

export default {
  name: 'BillView',
  components: {
    ModalBasic
  },
  setup() {
    const feedbackModalOpen = ref(false)
    return {
      feedbackModalOpen,
    }
  }
}

</script>
