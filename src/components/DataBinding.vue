<template>
  <form
    class="mx-20 mt-36 box-border max-w-[768px] border-2 border-black bg-white px-20 py-24 font-bold duration-150 hover:scale-105 lg:mx-auto"
  >
    <!-- email -->
    <div class="text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >email:</label
      >
      <p v-show="isSame" class="mt-2 inline text-center text-xs text-red-600">
        （無法輸入相同資料）
      </p>
      <input
        type="text"
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-sm duration-150 hover:border-gray-500"
        v-model="tempEmail"
        @keyup="inputEmail"
      />
    </div>
    <!-- password -->
    <div class="mt-10 text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >password:</label
      >
      <input
        type="text"
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-sm duration-150 hover:border-gray-500"
      />
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
    <!-- display data -->
    <div class="mt-16">
      <h2
        class="m-auto max-w-[30%] rounded-md border-2 border-black py-2 text-center text-lg uppercase text-black"
      >
        your data
      </h2>
      <div
        v-for="email in emails"
        :key="email"
        class="mx-4 mt-4 inline-block cursor-pointer border-2 border-black px-3 hover:bg-black hover:text-white"
      >
        <span @click="deleteItem(email)">{{ email }}</span>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      tempEmail: "",
      emails: [],
      isSame: false,
    };
  },
  methods: {
    inputEmail(e) {
      if (e.key === "Enter" && this.tempEmail) {
        if (!this.emails.includes(this.tempEmail)) {
          this.isSame = false;
          this.emails.push(this.tempEmail);
          this.tempEmail = "";
        } else {
          this.isSame = true;
        }
      }
    },
    deleteItem(email) {
      this.emails = this.emails.filter(item => email !== item);
    },
  },
};
</script>
