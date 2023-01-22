<template>
    

    <v-checkbox label="Checkbox"></v-checkbox>
    <v-checkbox label="Checkbox"></v-checkbox>
    <v-checkbox label="Checkbox"></v-checkbox>
    
  </template>
 
 
   
   <script >
     //
     export default {
     computed: {
       
     },
     data () {
         
       return {
        paymentDialog:false,
        notifications: false,
        sound: true,
        widgets: false,
       }
     },
     watch:{

     },
     methods:{

     },
   }
 
 
 
   
   </script>
 
 <style>
.dialog-bottom-transition-enter-active,
.dialog-bottom-transition-leave-active {
  transition: transform .2s ease-in-out;
}
</style>