<template>
<div class="container custom-font">
    <header>
    <nav class="navbar navbar-expand-sm   navbar-light bg-light">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo03" aria-controls="navbarTogglerDemo03" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
        <li class="nav-item">
          <nuxt-link to="/"><a class="nav-link" href="#">สินค้าทั้งหมด <span class="sr-only">(current)</span></a></nuxt-link>
        </li>
      <li class="nav-item">
        <a class="nav-link" href="#">บริการของเรา</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">ติดต่อเรา</a>
      </li>
      </ul>
      <div class="social-part">
        <i class="fa fa-facebook" aria-hidden="true"></i>
        <i class="fa fa-twitter" aria-hidden="true"></i>
        <i class="fa fa-instagram" aria-hidden="true"></i>
      </div>
    </div>
  </nav>
  </header>
 <div class="d-flex  align-items-center">
  <div class="row pt-3 mt-3">
    <!-- <div >สินค้าทั้งหมดมี {{ products.length }} รายการ</div> -->
            <div class="row col-md-12">
              <!-- card รายการสินค้า -->
              <div class="card p-2 col-md-4" v-for="(product,index) in products" :key="product.sku">
                  <div class="d-flex align-items-center ">
                      <div class="mt-2">
                          <h4 class="text-uppercase">{{ product.sku }}</h4>
                          <div class="mt-5">
                            <nuxt-link :to="`/products/${index}`"><h5 class="text-uppercase mb-0">{{ product.productName }}</h5></nuxt-link>
                              <h1 class="main-heading mt-0">฿{{ bathFormat(product.price) }}</h1>
                              <div class="d-flex flex-row p-4"></div>
                          </div>
                          <div class="image">
                              <!-- <img :src="product.imagePath" width="200"> -->
                              <img src="https://files.dezpax.com/products/202111240828205206.jpg" width="200">
                          </div>
                          
                      </div>
                      
                  </div>
                  <nuxt-link :to="`/products/${index}`"><button class="btn btn-info">ดูเพิ่มเติม</button></nuxt-link>
              </div>

            </div>
              
  </div>
</div>
</div> 

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
    </div> -->
  </template>
<script>
export default {
  data() {
    return {
      products: [],
    };
  },
  async mounted() {
    try {
      const response = await this.$axios.get('/products');
      this.products = response.data.productSet;
      console.log(this.products);
    } catch (error) {
      console.error(error);
    }
  },
  methods: {
    bathFormat(price) {
      // Implement your formatting logic here
      return price.toFixed(2);
    },
  },
};

// export default {
//   data() {
//     return {
//         products: [],
//         bathFormat
//     };
//   },
//   async mounted() {
//     try {
//       const response = await this.$axios.get('/products');
//       const data = await response.json();
//       this.products = data.productSet;
//       console.log(data.productSet);
//     } catch (error) {
//       console.error(error);
//     }
//   },
// };

// fetch--solution
// export default {
//   data() {
//     return {
//       products: [],
//       bathFormat
//     };
//   },
//   async mounted() {
//     try {
//       const response = await fetch('/products');
//       const data = await response.json();
//       this.products = data.productSet;
//       console.log(this.products);
//     } catch (error) {
//       console.error('Error:', error);
//     }
//   }
// };

/*
export default {
  data() {
    return {
      products: [],
      bathFormat
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
        {
            "sku": "SKU003",
            "productName": "สินค้าที่ 3",
            "imagePath": "https://example.com/image3.jpg",
            "price": 973,
            "description": "รายละเอียดสินค้าที่ 3",
            "size": "3",
            "weight": "300g"
        },
        {
            "sku": "SKU004",
            "productName": "สินค้าที่ 4",
            "imagePath": "https://example.com/image4.jpg",
            "price": 767,
            "description": "รายละเอียดสินค้าที่ 4",
            "size": "4",
            "weight": "400g"
        },
        {
            "sku": "SKU005",
            "productName": "สินค้าที่ 5",
            "imagePath": "https://example.com/image5.jpg",
            "price": 16,
            "description": "รายละเอียดสินค้าที่ 5",
            "size": "5",
            "weight": "500g"
        },
        {
            "sku": "SKU006",
            "productName": "สินค้าที่ 6",
            "imagePath": "https://example.com/image6.jpg",
            "price": 733,
            "description": "รายละเอียดสินค้าที่ 6",
            "size": "6",
            "weight": "600g"
        },
        {
            "sku": "SKU007",
            "productName": "สินค้าที่ 7",
            "imagePath": "https://example.com/image7.jpg",
            "price": 828,
            "description": "รายละเอียดสินค้าที่ 7",
            "size": "7",
            "weight": "700g"
        },
        {
            "sku": "SKU008",
            "productName": "สินค้าที่ 8",
            "imagePath": "https://example.com/image8.jpg",
            "price": 401,
            "description": "รายละเอียดสินค้าที่ 8",
            "size": "8",
            "weight": "800g"
        },
        {
            "sku": "SKU009",
            "productName": "สินค้าที่ 9",
            "imagePath": "https://example.com/image9.jpg",
            "price": 675,
            "description": "รายละเอียดสินค้าที่ 9",
            "size": "9",
            "weight": "900g"
        },
        {
            "sku": "SKU0010",
            "productName": "สินค้าที่ 10",
            "imagePath": "https://example.com/image10.jpg",
            "price": 678,
            "description": "รายละเอียดสินค้าที่ 10",
            "size": "10",
            "weight": "1000g"
        },
        {
            "sku": "SKU0011",
            "productName": "สินค้าที่ 11",
            "imagePath": "https://example.com/image11.jpg",
            "price": 544,
            "description": "รายละเอียดสินค้าที่ 11",
            "size": "11",
            "weight": "1100g"
        },
        {
            "sku": "SKU0012",
            "productName": "สินค้าที่ 12",
            "imagePath": "https://example.com/image12.jpg",
            "price": 813,
            "description": "รายละเอียดสินค้าที่ 12",
            "size": "12",
            "weight": "1200g"
        },
        {
            "sku": "SKU0013",
            "productName": "สินค้าที่ 13",
            "imagePath": "https://example.com/image13.jpg",
            "price": 99,
            "description": "รายละเอียดสินค้าที่ 13",
            "size": "13",
            "weight": "1300g"
        },
        {
            "sku": "SKU0014",
            "productName": "สินค้าที่ 14",
            "imagePath": "https://example.com/image14.jpg",
            "price": 531,
            "description": "รายละเอียดสินค้าที่ 14",
            "size": "14",
            "weight": "1400g"
        },
        {
            "sku": "SKU0015",
            "productName": "สินค้าที่ 15",
            "imagePath": "https://example.com/image15.jpg",
            "price": 109,
            "description": "รายละเอียดสินค้าที่ 15",
            "size": "15",
            "weight": "1500g"
        },
        {
            "sku": "SKU0016",
            "productName": "สินค้าที่ 16",
            "imagePath": "https://example.com/image16.jpg",
            "price": 21,
            "description": "รายละเอียดสินค้าที่ 16",
            "size": "16",
            "weight": "1600g"
        },
        {
            "sku": "SKU0017",
            "productName": "สินค้าที่ 17",
            "imagePath": "https://example.com/image17.jpg",
            "price": 703,
            "description": "รายละเอียดสินค้าที่ 17",
            "size": "17",
            "weight": "1700g"
        },
        {
            "sku": "SKU0018",
            "productName": "สินค้าที่ 18",
            "imagePath": "https://example.com/image18.jpg",
            "price": 263,
            "description": "รายละเอียดสินค้าที่ 18",
            "size": "18",
            "weight": "1800g"
        },
        {
            "sku": "SKU0019",
            "productName": "สินค้าที่ 19",
            "imagePath": "https://example.com/image19.jpg",
            "price": 825,
            "description": "รายละเอียดสินค้าที่ 19",
            "size": "19",
            "weight": "1900g"
        },
        {
            "sku": "SKU0020",
            "productName": "สินค้าที่ 20",
            "imagePath": "https://example.com/image20.jpg",
            "price": 720,
            "description": "รายละเอียดสินค้าที่ 20",
            "size": "20",
            "weight": "2000g"
        },
        {
            "sku": "SKU0021",
            "productName": "สินค้าที่ 21",
            "imagePath": "https://example.com/image21.jpg",
            "price": 442,
            "description": "รายละเอียดสินค้าที่ 21",
            "size": "21",
            "weight": "2100g"
        },
        {
            "sku": "SKU0022",
            "productName": "สินค้าที่ 22",
            "imagePath": "https://example.com/image22.jpg",
            "price": 200,
            "description": "รายละเอียดสินค้าที่ 22",
            "size": "22",
            "weight": "2200g"
        },
        {
            "sku": "SKU0023",
            "productName": "สินค้าที่ 23",
            "imagePath": "https://example.com/image23.jpg",
            "price": 762,
            "description": "รายละเอียดสินค้าที่ 23",
            "size": "23",
            "weight": "2300g"
        },
        {
            "sku": "SKU0024",
            "productName": "สินค้าที่ 24",
            "imagePath": "https://example.com/image24.jpg",
            "price": 80,
            "description": "รายละเอียดสินค้าที่ 24",
            "size": "24",
            "weight": "2400g"
        },
        {
            "sku": "SKU0025",
            "productName": "สินค้าที่ 25",
            "imagePath": "https://example.com/image25.jpg",
            "price": 199,
            "description": "รายละเอียดสินค้าที่ 25",
            "size": "25",
            "weight": "2500g"
        }
    ]
};
       const dataList = await data;
      this.products = dataList.productSet;
    } catch (error) {
      console.error('Error:', error);
    }
  }
};
*/



</script>
<style scoped>
body{
    background-color:#dce3f0;
    
}
.custom-font{
    font-family: 'kanitregular';
}
.height{
    
    height:100vh;
}

.card{
    width:350px;
    height:300px;
}

.image{
    position:absolute;
    right:12px;
    top:5px;
    bottom:20px;
}

.main-heading{
    
    font-size:25px;
    color:#0098ef !important;
}

.truncate {
  width: 200px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>