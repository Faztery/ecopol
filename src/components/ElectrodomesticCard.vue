<template>
    
		<button
		
			class="mt-2 p-4 flex justify-between bg-gray-300 rounded-lg
			font-semibold capitalize">
			<!-- link -->

			<div class="flex">

				<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                </svg>

				<div class="flex flex-col text-left ml-4">

					<span>{{name}}</span>
					<span class="text-sm text-gray-600">Consumo: {{power}}W</span>

				</div>

			</div>

			<span>$ {{avgprice}}</span>

		</button>

</template>

<script>
export default {
    props:['name','power','avgprice']
}
</script>