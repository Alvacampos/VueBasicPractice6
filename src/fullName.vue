<template>
<div class="row" style="margin:5px">
  <input 
    type="text" 
    placeholder="First Name" 
    :value='firstName'
    @input="nameChanged(true, $event)">
  <input 
    type="text" 
    placeholder="Last Name" 
    :value="lastName"
    @input="nameChanged(false, $event)">
  </div>  
</template>

<script>
  export default {
    props: ['value'],
    methods: {
      nameChanged(isFirst, event) {
        let name = ''
        if(isFirst){
          name= event.target.value + ' ' + this.lastName;
        } else {
          name= this.firstName + ' ' + event.target.value;
        }
        this.value=name;
        this.$emit('input', this.value);
      }
    },
    computed: {
      firstName() {
        return this.value.split(' ')[0];
      },
      lastName() {
        return this.value.split(' ')[1];
      }
    },    
  }
  
</script>

<style>
  
</style>