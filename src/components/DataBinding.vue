<template>
  <div
    class="mx-20 mt-10 box-border max-w-[768px] border-2 border-black bg-white px-20 py-24 font-bold duration-150 hover:scale-105 lg:mx-auto"
  >
    <div class="text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >email:</label
      >
      <input
        type="text"
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-sm duration-150 hover:border-gray-500"
      />
    </div>
    <div class="mt-10 text-lg text-black">
      <label class="inline-block text-sm uppercase tracking-wider"
        >password:</label
      >
      <input
        type="text"
        class="outline-none mt-1 box-border block w-full rounded-sm border-2 px-1 py-1 text-sm duration-150 hover:border-gray-500"
      />
    </div>
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
      <div class="flex items-center mt-10 text-lg text-black">
        <input
          type="checkbox"
          class="w-4 h-4"
        />
        <label class="ml-4 text-sm uppercase tracking-wider"
          >accept terms and conditions</label
        >
      </div>
    </div>
  </div>
</template>
