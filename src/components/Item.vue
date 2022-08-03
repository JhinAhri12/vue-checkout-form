<template>
    <div v-for="item in items" :key="item.id" class="d-flex p-3">
        <div class="col-2"></div>
        <div class="col-3 me-5">
            <img src="https://randomwordgenerator.com/img/picture-generator/51e4d0404f4faa0df7c5d57bc32f3e7b1d3ac3e456597948702d7cdc97_640.jpg" alt="" class="" style="height: 100%;width: 120px;object-fit: cover;"> 
        </div>
        <div class="col-3">
            <h3>{{item.title}}</h3>
            <p>{{item.description}}</p>
            <b>{{item.price}} €</b>
        </div>
        
        <div class="col-2"></div>
    </div>
    
</template>

<script>
export default {
    name: "Item",
    props: {
    items: Array
  }
}
</script>