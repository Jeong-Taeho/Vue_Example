<template>
  <div class="black-bg" v-if="openmodal">
    <div class="white-bg">
      <h4>{{products[modalclick].title}}</h4>
      <p>{{products[modalclick].price}}만원</p>
      <!-- <button class="modal-btn" @click="openmodal = false">close</button>    -->
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal-item',
    props : {
        products : Array,
        modalclick : Number,
        openmodal : Boolean,
    }
}
</script>

<style>

</style>