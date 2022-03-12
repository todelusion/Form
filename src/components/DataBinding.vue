<template>
  <div
    class="mx-20 mt-36 box-border max-w-[768px] border-2 border-black bg-white px-20 py-24 font-bold lg:mx-auto"
  >
    <!-- intrest-->
    <div class="text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >Interests</label
      >
      <p v-show="isSame" class="mt-2 inline text-center text-xs text-red-600">
        （無法輸入相同資料）
      </p>
      <input
        type="text"
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-sm duration-150 hover:border-gray-500"
        v-model="tempdata"
        @keyup="inputdata"
      />
    </div>
        <!-- display data -->
    <div class="mt-3">
      <div
        v-for="data in datas"
        :key="data"
        class="mr-4 mt-4 inline-block cursor-pointer border-2 border-black px-3 hover:bg-black hover:text-white"
      >
        <span @click="deleteItem(data)">{{ data }}</span>
      </div>
    </div>
    <!-- career -->
    <div class="mt-10 text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >career</label
      >
      <select
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-lg duration-150 hover:border-gray-500"
      >
        <option value="front-end">Front End Engineer</option>
        <option value="back-end">Back End Engineer</option>
        <option value="designer">UI/UX Desinger</option>
      </select>
      <div class="mt-10 flex items-center text-lg text-black">
        <label
          class="flex cursor-pointer select-none items-center text-sm uppercase tracking-wider"
          ><input type="checkbox" class="h-4 w-4" /><span class="ml-5"
            >accept terms and conditions</span
          ></label
        >
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      tempdata: "",
      datas: [],
      isSame: false,
    };
  },
  methods: {
    inputdata(e) {
      if (e.key === "Enter" && this.tempdata) {
        if (!this.datas.includes(this.tempdata)) {
          this.isSame = false;
          this.datas.push(this.tempdata);
          this.tempdata = "";
        } else {
          this.isSame = true;
        }
      }
    },
    deleteItem(data) {
      this.datas = this.datas.filter(item => data !== item);
    },
  },
};
</script>
