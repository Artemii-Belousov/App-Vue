<template>
  <tr>
    <td class="td">{{ item.id }}</td>
    <td class="td">{{ item.date}}</td>
    <td class="td">{{ item.category}}</td>
    <td class="td">{{ item.value}}</td>
    <td  
      v-on:click="$emit('remove-item', item.id)"
    ><button class="rm">&times;</button></td>
  </tr>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  
};
</script>

<style>
.rm{
  background: red;
  color: #ffffff;
  border: none;
}
</style>
