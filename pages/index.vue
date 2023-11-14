<script lang="ts" setup>

const sheetBottomProfileShow = ref(false);
const onSheetBottomProfileToggle = () => {
  sheetBottomProfileShow.value = !sheetBottomProfileShow.value;
};

const sheetBottomNotifShow = ref(false);
const onSheetBottomNotifToggle = () => {
  sheetBottomNotifShow.value = !sheetBottomNotifShow.value;
};

</script>

<template>
  <BarTop @profile-click="onSheetBottomProfileToggle" @notif-click="onSheetBottomNotifToggle" />
  <h1>welcome</h1>

  <BSheetBottom :show="sheetBottomProfileShow" @close="onSheetBottomProfileToggle">
    <div class="px-5">
      <div class="flex items-center justify-between">
        <div class="flex items-center space-x-3">
          <BAvatar src="https://www.jokesforfunny.com/wp-content/uploads/2021/06/0596bdb89b60fe771acd2f5972a9d3e3.jpg" size="sm" @click="$emit('profileClick')" />
          <div class="flex flex-col">
            <span class="font-bold">Hadi Hammurabi</span>
            <span>hadihammurabi@gmail.com</span>
          </div>
        </div>
        <BButton size="icon" variant="danger"><div class="i-uil-exit"></div></BButton>
      </div>
    </div>
  </BSheetBottom>

  <BSheetBottom :show="sheetBottomNotifShow" @close="onSheetBottomNotifToggle">
    <div class="flex flex-col">
      <div class="px-3 py-3 flex justify-between items-start hover:bg-slate-100">
        <div class="flex items-start space-x-3 w-11/12">
          <BAvatar src="https://www.jokesforfunny.com/wp-content/uploads/2021/06/0596bdb89b60fe771acd2f5972a9d3e3.jpg" size="sm" @click="$emit('profileClick')" />
          <div class="flex flex-col w-3/4">
            <span>+1 Like</span>
            <span class="text-slate text-sm">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum id hic...</span>
          </div>
        </div>
        <div class="h-[10px] w-[10px] rounded-full bg-green"></div>
      </div>

      <div class="px-3 py-3 flex justify-between items-start hover:bg-slate-100">
        <div class="flex items-start space-x-3 w-11/12">
          <BAvatar src="https://www.jokesforfunny.com/wp-content/uploads/2021/06/0596bdb89b60fe771acd2f5972a9d3e3.jpg" size="sm" @click="$emit('profileClick')" />
          <div class="flex flex-col">
            <span>New Comment from Alex</span>
            <span class="text-slate text-sm">Lorem ipsum dolor, sit amet consectetur adipisicing</span>
          </div>
        </div>
        <div class="h-[10px] w-[10px] rounded-full bg-green"></div>
      </div>

    </div>
  </BSheetBottom>

</template>
