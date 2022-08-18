<template>
  <div class="bill">
    <h1>AQUI VA EL CONTENIDO</h1>

    <button class="btn bg-indigo-500 hover:bg-indigo-600 text-white" aria-controls="feedback-modal"
      @click.stop="feedbackModalOpen = true">Send Feedback</button>
    <ModalBasic id="basic-modal" :modalOpen="basicModalOpen" @close-modal="basicModalOpen = false" title="Basic Modal">
      <!-- Modal content -->
      <div class="px-5 pt-4 pb-1">
        <div class="text-sm">
          <div class="font-medium text-slate-800 mb-2">Let’s Talk Paragraph</div>
          <div class="space-y-2">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
              dolore magna aliqua.</p>
            <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
              Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est
              laborum.</p>
          </div>
        </div>
      </div>
      <!-- Modal footer -->
      <div class="px-5 py-4">
        <div class="flex flex-wrap justify-end space-x-2">
          <button class="btn-sm border-slate-200 hover:border-slate-300 text-slate-600"
            @click.stop="basicModalOpen = false">Close</button>
          <button class="btn-sm bg-indigo-500 hover:bg-indigo-600 text-white">I Understand</button>
        </div>
      </div>
    </ModalBasic>

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
