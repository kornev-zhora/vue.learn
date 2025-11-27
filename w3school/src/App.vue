<template>
  <h1>App.vue</h1>


  <slot-comp>

    <template #leftSlot="leftProps">
      <div>{{ leftProps.text }}</div>
    </template>

    <template #rightSlot="rightProps">
      <div>{{ rightProps.text }}</div>
    </template>

  </slot-comp>


</template>



<script>
import SlotComp from './components/SlotComp.vue';

export default {
  data() {
    return {
      newItem: '',
      items: ['Buy apples','Make pizza','Mow the lawn'],
      foods: ['Apples','Pizza','Rice','Fish','Cake']
    };
  },
  methods: {
    addItem() {
      this.items.push(this.newItem),
          this.newItem = '';
    }
  },
  components: {
    'slot-comp': SlotComp
  }
}

</script>
