<script lang="ts" setup>
const sheetBottomShow = ref(false);
const onSheetBottomToggle = () => {
  sheetBottomShow.value = !sheetBottomShow.value;
};
</script>

<template>
  <BarTop @profile-click="onSheetBottomToggle" />
  <h1>welcome</h1>

  <SheetBottom :show="sheetBottomShow" @close="onSheetBottomToggle">
    <div class="px-5">
      <div class="flex items-center justify-between">
        <div class="flex items-center space-x-3">
          <Avatar src="https://www.jokesforfunny.com/wp-content/uploads/2021/06/0596bdb89b60fe771acd2f5972a9d3e3.jpg" size="sm" @click="$emit('profileClick')" />
          <div class="flex flex-col">
            <span class="font-bold">Hadi Hammurabi</span>
            <span>hadihammurabi@gmail.com</span>
          </div>
        </div>
        <Button size="icon" variant="danger"><div class="i-uil-exit"></div></Button>
      </div>
    </div>
  </SheetBottom>

</template>
