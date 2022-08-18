<template>
  <div class="bill">
    <h1>AQUI VA EL CONTENIDO</h1>
    <div class="flex gap-3">
      <button class="btn bg-indigo-500 hover:bg-indigo-600 text-white" aria-controls="feedback-modal"
        @click.stop="addModalOpen = true">Agregar electrodoméstico</button>
      <button class="btn bg-indigo-500 hover:bg-indigo-600 text-white" aria-controls="feedback-modal"
        @click.stop="editModalOpen = true">E</button>
    </div>
    <ModalBasic id="feedback-modal" :modalOpen="addModalOpen" @close-modal="addModalOpen = false"
      title="Agregar electrodoméstico">
      <!-- Modal content -->
      <div class="px-5 py-4">
        <div class="text-sm">
          <div class="font-medium text-slate-800 mb-3">Agrega toda la información necesaria del consumo por hora de un
            electrodoméstico 🙌</div>
        </div>
        <div class="space-y-3">
          <div class="flex flex-col justify-items-start items-start">
            <label class="block text-sm font-medium mb-1" for="name">Nombre del electrodoméstico</label>
            <Input v-model="data.name" type="text" placeholder="Ingresa el nombre del electrodoméstico" required />
            <div class="text-xs text-red-500 italic mt-2">{{ errorsForm1["name"] }} </div>
          </div>
          <div class="flex flex-col justify-items-start items-start">
            <label class="block text-sm font-medium mb-1" for="name">Horas de consumo diario</label>
            <Input v-model="data.hours" type="text" placeholder="Ingreso de horas de consumo diario" required />
            <div class="text-xs text-red-500 italic mt-2">{{ errorsForm1["hours"] }} </div>
          </div>
          <div class="flex flex-col justify-items-start items-start">
            <label class="block text-sm font-medium mb-1" for="name">Consumo del electrodoméstico en (W/h)</label>
            <Input v-model="data.consumption" type="text" placeholder="Ingrese el consumo de electrodoméstico en (W/h)"
              required />
            <div class="text-xs text-red-500 italic mt-2">{{ errorsForm1["consumption"] }} </div>
          </div>
        </div>
        <!-- Modal footer -->
        <div class="px-5 py-4 border-t border-slate-200">
          <div class="flex flex-wrap justify-end space-x-2">
            <button class="btn-sm border-slate-200 hover:border-slate-300 text-slate-600"
              @click="addModalOpen = false">Cancelar</button>
            <button @click="sendForm1" class="btn-sm bg-indigo-500 hover:bg-indigo-600 text-white">Agregar</button>
          </div>
        </div>
      </div>
    </ModalBasic>
    <ModalBasic id="feedback-modal" :modalOpen="editModalOpen" @close-modal="editModalOpen = false"
      title="Editar consumo eléctrico">
      <!-- Modal content -->
      <div class="px-5 py-4">
        <div class="text-sm">
          <div class="font-medium text-slate-800 mb-3">Edita el valor del consumo eléctrico mensual🙌</div>
        </div>
        <div class="space-y-3">
          <div class="flex flex-col justify-items-start items-start">
            <label class="block text-sm font-medium mb-1" for="name"></label>
            <Input type="text" v-model="energyPrice" placeholder="Ingrese costo mensual de energía" required />
            <div class="text-xs text-red-500 italic mt-2">{{ errorsForm2["energyPrice"] }} </div>
          </div>
        </div>
        <!-- Modal footer -->
        <div class="px-5 py-4 border-t border-slate-200">
          <div class="flex flex-wrap justify-end space-x-2">
            <button class="btn-sm border-slate-200 hover:border-slate-300 text-slate-600"
              @click="editModalOpen = false">Cancelar</button>
            <button @click="sendForm2" class="btn-sm bg-indigo-500 hover:bg-indigo-600 text-white">Editar</button>
          </div>
        </div>
      </div>
    </ModalBasic>
  </div>
</template>
<script>
import { ref } from 'vue';
import ModalBasic from '../components/ModalBasic';
import Input from '../components/Input';

export default {
  name: 'BillView',
  components: {
    ModalBasic,
    Input
  },
  setup() {
    const addModalOpen = ref(false)
    const editModalOpen = ref(false)
    const energyPrice = ref(0.096)
    const errorsForm1 = ref({})
    const errorsForm2 = ref({})
    const data = ref({ name: null, hours: null, consumption: null })
    return {
      addModalOpen,
      editModalOpen,
      energyPrice,
      errorsForm2,
      data,
      errorsForm1,
    }
  },
  methods: {
    isNumeric: function (n) {
      return !isNaN(parseFloat(n)) && isFinite(n);
    },
    sendForm1: function () {
      if (this.checkForm1()) {
        this.addModalOpen = false;
      }
    },
    sendForm2: function () {
      if (this.checkForm2()) {
        this.editModalOpen = false;
      }
    },
    checkForm1: function () {
      console.log("hola")
      if (this.data.name && this.data.hours && this.data.consumption) {
        return true;
      }
      this.errorsForm1 = {};
      if (!this.data.name) {
        this.errorsForm1.name = 'El nombre del electrodoméstico es requerido';
      }
      if (!this.data.hours) {
        this.errorsForm1.hours = 'Las horas de consumo son requeridas';
      }
      if (!this.isNumeric(this.data.hours)) {
        this.errorsForm1.hours = 'Las horas de consumo deben ser numéricas';
      }
      if (!this.data.consumption) {
        this.errorsForm1.consumption = 'El consumo del electrodoméstico es requerido';
      }
      if (!this.isNumeric(this.data.consumption)) {
        this.errorsForm1.consumption = 'El consumo del electrodoméstico debe ser numérico';
      }
      return false;
    },
    checkForm2: function () {
      if (this.energyPrice) {
        return true;
      }
      this.errorsForm2 = {};
      if (!this.energyPrice) {
        this.errorsForm2.energyPrice = 'El costo de energía es requerido';
      }
      if (!this.isNumeric(this.energyPrice)) {
        this.errorsForm2.energyPrice = 'El costo de energía debe ser numérico';
      }
      return false;
    }
  }
}

</script>
