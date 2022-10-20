<template>
  <div class="w-screen h-screen flex items-center justify-center">
    <button @click="getRoomList()" class="bg-[#feb401] px-4 py-1.5 rounded-lg">getRoomList</button>
  </div>
</template>
<script lang="ts" setup>
  const api = inject('$api') as any

  const query = {
    pageNo: 1,
    pageSize: 3
  }

  const getRoomList = async () => {
    const { result } = await api.room.getRoomList(query)
    console.log(result)
  }

  getRoomList()

  const loadingStore = inject<any>('$stores').loadingStore()

  console.log(loadingStore)
</script>
