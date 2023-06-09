<template>
  <div class="pt-3 custom-font">
    <center><h1>PAX PAX SHOP</h1></center>
    <ProductList />
  </div>
</template>

<script>
import ProductList from '@/components/product_list_all.vue';

export default {
  components: {
    ProductList
  }
};
</script>


<!-- pages/ExamplePage.vue -->
<!-- <template>
  <div>
    <h1>รายการสินค้า ทั้งหมด</h1>
    <ul>
      <li v-for="item in items" :key="item.forms">{{ item.forms.ditto }}</li>
    </ul>
  </div>
</template> -->

<!-- <template> -->

  <!-- <div class="container">
    <div class="row">
      <div class="col-md-4" v-for="product in products" :key="product.sku">
        <div class="card">
          <img :src="product.imagePath" class="card-img-top" alt="Product Image">
          <div class="card-body">
            <h5 class="card-title">{{ product.productName }}</h5>
            <p class="card-text">{{ product.description }}</p>
            <p>Price: {{ product.price }}</p>
            <p>Size: {{ product.size }}</p>
            <p>Weight: {{ product.weight }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template> -->

<!-- ดึง API -->
<!-- <script>
export default {
  data() {
    return {
      products: []
    };
  },
  async mounted() {
    try {
      const response = await fetch('http://10.0.7.69:3001/products');
      const data = await response.json();
      this.products = data.productSet;
      console.log(this.products);
    } catch (error) {
      console.error('Error:', error);
    }
  }
};
</script> -->

<!-- fixed data test  -->
<!-- <script>
export default {
  data() {
    return {
      products: []
    };
  },
  async mounted() {
    try {
      const data =   {
          "productSet": [
              {
                  "sku": "SKU001",
                  "productName": "สินค้าที่ 1",
                  "imagePath": "https://example.com/image1.jpg",
                  "price": 711,
                  "description": "รายละเอียดสินค้าที่ 1",
                  "size": "1",
                  "weight": "100g"
              },
              {
                  "sku": "SKU002",
                  "productName": "สินค้าที่ 2",
                  "imagePath": "https://example.com/image2.jpg",
                  "price": 215,
                  "description": "รายละเอียดสินค้าที่ 2",
                  "size": "2",
                  "weight": "200g"
              },
              
          ]
      };
       const dataList = await data;
      this.products = dataList.productSet;
    } catch (error) {
      console.error('Error:', error);
    }
  }
};
</script> -->

<!-- <template>
  <Tutorial />
</template>

<script>
export default {
  name: 'IndexPage',
}
</script> -->
<style scoped>
.custom-font{
    font-family: 'kanitregular';
}
</style>
