<template>
    <div class="container ">
        <div class="row mt-4">
            <div class="col-md-1"></div>
            <div class="col-md-6 me-4">
                <h2>Payment Information</h2>
                <div class="bg-white">
                    <Card />
                    <div class="m-4">
                        <CardForm :total="total" />
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <h2>Order Summary</h2>
                <div class="bg-white">
                    <Item :items="items" />
                </div>
            </div>
            <div class="col-md-1"></div>
        </div>
    </div>
</template>

<script>
import Card from "../components/Card.vue";
import CardForm from "../components/CardForm.vue";
import Item from "../components/Item.vue";

export default {
  name: "PaymentPage",
  components: {
    Card,
    CardForm,
    Item
    
  },
    data(){
      return {
        items : [{
                id: 1,
                title : 'Title 1',
                description : 'lorem ipsum',
                price: 120
        },
        {
                id: 2,
                title : 'Title 2',
                description : 'lorem ipsum',
                price: 10
        },
        {
                id: 3,
                title : 'Title 3',
                description : 'lorem ipsum',
                price: 20
        }
        ],
        total: 0
    }
  },
    mounted() {
    this.getTotal(this.items);
  },
  methods: {
    getTotal(items) {
      items.forEach(item => {
        this.total += item.price;
      });
    }
  }
}
</script>
