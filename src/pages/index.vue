<template>
  <div class="w-screen h-screen flex items-center justify-center">
    <button @click="getRoomList()" class="bg-[#feb401] px-4 py-1.5 rounded-lg">getRoomList</button>
  </div>
</template>
<script lang="ts" setup>
  const api = inject<any>('$api')

  const query = {
    pageNo: 1,
    pageSize: 3
  }

  function getRoomList (): void {
    api.room.getRoomList(query)
    .then((res: any) => console.log(res.result))
    .catch((err: any) => console.log(err))
  }

  getRoomList()

  const loadingStore = inject<any>('$stores').loadingStore()

  console.log(loadingStore)
</script>
