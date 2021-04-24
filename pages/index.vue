<template>
  <div class="w-screen h-screen bg-yellow-500 p-20">
    <div class="text-blue-700 text-2xl">
      parent
      <i class="fas fa-home"></i>
    </div>
    <div class="flex w-full bg-blue-500 md:bg-red-500 p-14">
      child 1
            <testimonial></testimonial>
    </div>
        <div class="flex w-full bg-red-500 md:bg-blue-500 p-14">
      child 2 {{productName}}
        <testimonial
          img_src="https://images.unsplash.com/photo-1499714608240-22fc6ad53fb2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=334&q=80Q"
          name="Ray"
          title="Hey"
          content="lorem ipsum">
        </testimonial>
    </div>
  </div>
</template>

<script>
import { mapActions, mapState } from 'vuex';

export default {
  layout: "layout_a",
  computed:{
    ...mapState({
        productName: state => state.product.productName
    })
  },
  methods:{
    ...mapActions({
      getProduct:"product/getProduct"
    })
  },
  mounted(){
    this.getProduct();
  }
}
</script>

<style>
</style>
