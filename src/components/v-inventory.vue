<template>
  <div class="v-inventory">
    <div
      class="v-inventory__items droppable"
      @drop="onDrop($event, slot.id)"
      v-for="slot in slots"
      :key="slot.id"
      @dragover.prevent
      @dragenter.prevent
    >
      <div
        class="v-inventory__items_item draggable"
        v-for="item in items.filter(x => x.slotId === slot.id)"
        :key="item"
        @dragStart="onDragStart($event, item)"
        draggable="true"
        @click="openMenu"
      >
        <p id="square"></p>
        <div class="item-count">{{ item.count }}</div>
      </div>
    </div>
  </div>
</template>
  
  <script>
import { ref } from "vue";
export default {
  name: "vInventory",
  setup() {
    const items = ref([
      {
        id: 0,
        title: `item`,
        slotId: 2,
        count: 5,
      },
      {
        id: 1,
        title: "item",
        slotId: 16,
        count: 2,
      },
      {
        id: 2,
        title: "item",
        slotId: 6,
        count: 7,
      },
    ]);
    const slots = ref([
      { id: 1 }, { id: 2 }, { id: 3 }, { id: 4 }, { id: 5 },
      { id: 6 }, { id: 7 }, { id: 8 }, { id: 9 }, { id: 10 },
      { id: 11 }, { id: 12 }, { id: 13 }, { id: 14 }, { id: 15 },
      { id: 16 }, { id: 17 }, { id: 18 }, { id: 19 }, { id: 20 },
      { id: 21 }, { id: 22 }, { id: 23 }, { id: 24 }, { id: 25 },
      
    ]);

    function onDragStart(e, item) {
      e.dataTransfer.dropEffect = "move";
      e.dataTransfer.effectAllowed = "move";
      e.dataTransfer.setData("itemId", item.id);
    }
    function onDrop(e, slotId) {
      const itemId = e.dataTransfer.getData("itemId");
      items.value = items.value.map(x => {
        if (x.id == itemId) 
        x.slotId = slotId;
        return x;
      });
    }
    function openMenu(){
        console.log('open menu');
    
    }

    return {
      items,
      slots,
      onDragStart,
      onDrop,
      openMenu
    };
  },
};
</script>
  
  <style lang="scss">
.v-inventory {
  border: 1px solid #4d4d4d;
  border-radius: 20px;
  background: #292929;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  width: 800px;
  overflow: hidden;
  &__items {
    position: relative;
    border: 1px solid #4d4d4d;
    overflow: hidden;
    &_item {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
    }
  }
}
.item-count {
  position: absolute;
  bottom: 0;
  right: 0;
  border: 1px solid #4d4d4d;
  border-top-left-radius: 5px;
  padding: 1px 4px;
}

#square {
  width: 40%;
  height: 40%;
  background: rgba(173, 216, 230, 0.658);
  filter: blur(1px);
  opacity: 0.5;
  &::after {
    background: #6e5c5c;
    background-position: 20% 20%;
    z-index: 1;
    filter: blur(radius);
  }
}
</style>