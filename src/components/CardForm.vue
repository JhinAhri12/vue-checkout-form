<template>
<form>
  <div class="mb-3">
    <label for="nc" class="form-label">Name on Card</label>
    <input type="text" v-model="nameCard" class="form-control" id="nc">
  </div>
  <div class="mb-3">
    <label for="cn" class="form-label">Card Number</label>
    <input type="number" v-model="numberCard" class="form-control" id="cn">
  </div>
  Expiration Date
    <div class="row mb-4">
        <div class="col-4">
            <input type="number"  v-model="month" class="form-control" placeholder="Month" id="">
        </div>
        <div class="col-4">
            <input type="number"  v-model="year" class="form-control" placeholder="Year" id="">
        </div>
        <div class="col-4">
            <input type="number"  v-model="cvc" class="form-control" placeholder="CVC" id="">
        </div>
    </div>
    <div class="row">
        <div class="col-10"></div>
        <div class="col-2"><b>{{total}}€</b></div>
    </div><br>
    <div class="text-center">
        
        <button type="submit" @click.prevent="submitPayment" class="btn btn-primary btn-lg mb-3">Confirm Payment</button>
    </div>
  
</form>
</template>

<script>
export default {
  name: "CardForm",
  props: {
    total: Number
  },
  data(){
      return(
          {
              numberCard : '',
              nameCard : '',
              month : '',
              year : '',
              cvc : ''
          }
      )
  },
  methods: {
      submitPayment(){
          if(this.numberCard && this.nameCard && this.month && this.year && this.cvc)
          {
            alert("Payment successfull")
          }
          else {
              alert("Please complete the form")
          }
      }
  }
}
</script>