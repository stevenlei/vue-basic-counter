<script>
export default {
  data() {
    return {
      numberX: 0,
      numberY: 0,
    };
  },
  computed: {
    numberZ() {
      return this.numberX + this.numberY;
    },
  },
  watch: {
    numberX(newValue) {
      this.numberY = newValue;
    },
  },
};
</script>

<template>
  <div class="min-h-screen w-full bg-slate-100 flex justify-center items-center">
    <div class="bg-white flex-1 max-w-md rounded-xl shadow-xl overflow-hidden">
      <input
        class="text-9xl font-semibold text-center text-gray-800 py-12 w-full outline-none"
        v-model.number="numberX"
      />
      <div class="flex">
        <button
          class="bg-blue-600 py-4 font-mono text-center flex-1 text-5xl text-white hover:bg-blue-700"
          @click="numberX--"
        >
          -
        </button>
        <button
          class="bg-blue-500 py-4 font-mono text-center flex-1 text-5xl text-white hover:bg-blue-700"
          @click="numberX++"
        >
          +
        </button>
      </div>
    </div>
    <div class="text-9xl font-mono p-20">+</div>
    <div class="bg-white flex-1 max-w-md rounded-xl shadow-xl overflow-hidden">
      <input
        class="text-9xl font-semibold text-center text-gray-800 py-12 w-full outline-none"
        v-model.number="numberY"
      />
      <div class="flex">
        <button
          class="bg-blue-600 py-4 font-mono text-center flex-1 text-5xl text-white hover:bg-blue-700"
          @click="numberY--"
        >
          -
        </button>
        <button
          class="bg-blue-500 py-4 font-mono text-center flex-1 text-5xl text-white hover:bg-blue-700"
          @click="numberY++"
        >
          +
        </button>
      </div>
    </div>
    <div class="text-9xl font-mono p-20">
      = <span class="font-sans font-bold">{{ numberZ }}</span>
    </div>
  </div>
</template>
