<template>
    <div class="container custom-font">
        <header>
            <nav class="navbar navbar-expand-sm   navbar-light bg-light">
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo03"
                    aria-controls="navbarTogglerDemo03" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
                    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
                        <li class="nav-item">
                            <nuxt-link to="/"><a class="nav-link" href="#">สินค้าทั้งหมด <span
                                        class="sr-only">(current)</span></a></nuxt-link>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">บริการของเรา</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#">ติดต่อเรา</a>
                        </li>
                    </ul>
                    <div class="social-part">
                        <div>สินค้าทั้งหมดมี {{ products.length }} รายการ</div>
                    </div>
                </div>
            </nav>
        </header>
        <div class="d-flex  align-items-center">
            <div class="row pt-3 mt-3">
                <div class="row col-md-12">
                    <div class="col-md-4" v-for="(product, index) in products" :key="product.sku">
                        <div class="container py-3">
                            <div class="justify-content-center">
                                <!-- <div class="col-md-8 col-lg-6 col-xl-4"> -->
                                <div class="card content-img"><center>
                                    <nuxt-link :to="`/products/${index}`">
                                        <img :src="getImageURL(product.imagePath)" :alt="product.productName"
                                            class="card-img-top">
                                    </nuxt-link>
                                    </center>
                                    <div class="card-body">
                                        <div class="text-center">
                                            <h5 class="card-title">{{ product.sku }}</h5>
                                            <nuxt-link :to="`/products/${index}`">
                                                <p class="text-muted mb-4">{{ product.productName }}</p>
                                            </nuxt-link>
                                        </div>
                                        <div class="d-flex justify-content-between total font-weight-bold mt-4">
                                            <span>ราคาสินค้า :</span><span>฿{{ bathFormat(product.price) }}</span>
                                        </div>
                                    </div>
                                </div>
                                <!-- </div> -->
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
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
            // console.log(this.products);
        } catch (error) {
            console.error(error);
        }
    },
    methods: {
        bathFormat(price) {
            // Implement your formatting logic here
            return price.toFixed(2);
        },
        getImageURL(imagePath) {
        if (!imagePath) {
            // Handle the case when imagePath is undefined
            return ''; // Return a default value or an appropriate fallback image URL
        }
        return `${process.env.BASE_URL}${imagePath}`;
        },
    },
};


</script>
<style scoped>
/* .content-img{
    width: 100%;
    height: 250px;
} */
.card-img,
.card-img-bottom,
.card-img-top {
    width: 310px;
    height: 310px;
}

.card-img,
.card-img-top {
    border-top-left-radius: var(--mdb-card-inner-border-radius);
    border-top-right-radius: var(--mdb-card-inner-border-radius)
}

.card-img,
.card-img-bottom {
    border-bottom-right-radius: var(--mdb-card-inner-border-radius);
    border-bottom-left-radius: var(--mdb-card-inner-border-radius)
}

.card-group>.card {
    margin-bottom: var(--mdb-card-group-margin)
}

@media(min-width: 576px) {
    .card-group {
        display: flex;
        flex-flow: row wrap
    }

    .card-group>.card {
        flex: 1 0 0%;
        margin-bottom: 0
    }

    .card-group>.card+.card {
        margin-left: 0;
        border-left: 0
    }

    .card-group>.card:not(:last-child) {
        border-top-right-radius: 0;
        border-bottom-right-radius: 0
    }

    .card-group>.card:not(:last-child) .card-header,
    .card-group>.card:not(:last-child) .card-img-top {
        border-top-right-radius: 0
    }

    .card-group>.card:not(:last-child) .card-footer,
    .card-group>.card:not(:last-child) .card-img-bottom {
        border-bottom-right-radius: 0
    }

    .card-group>.card:not(:first-child) {
        border-top-left-radius: 0;
        border-bottom-left-radius: 0
    }

    .card-group>.card:not(:first-child) .card-header,
    .card-group>.card:not(:first-child) .card-img-top {
        border-top-left-radius: 0
    }

    .card-group>.card:not(:first-child) .card-footer,
    .card-group>.card:not(:first-child) .card-img-bottom {
        border-bottom-left-radius: 0
    }
}

.custom-font {
    font-family: 'kanitregular';
}

/* 
.height {

    height: 100vh;
}

.card {
    width: 350px;
    height: 300px;
}

.image {
    position: absolute;
    right: 12px;
    top: 5px;
    bottom: 20px;
}

.main-heading {

    font-size: 25px;
    color: #0098ef !important;
} */

.truncate {
    width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}</style>