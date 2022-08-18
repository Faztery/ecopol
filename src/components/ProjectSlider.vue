<script setup>
import { reactive, computed, defineProps } from 'vue'
const props = defineProps({
    first: {
        type: Boolean,
        default: false
    }
}
)


</script>

<template>
    <!-- El primer FullScreen Div en cada View necesita usar -mt-0 pt-0 si el header es sticky -->
    <div class="p-8 min-h-screen">
        
        <slot/>
        
    </div>
</template>
