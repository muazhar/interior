<template>
  <q-page>
    <div class="diagonal-box bg-one">
      <div class="flex flex-center text-white" style="height:600px">
        <q-card flat class="bg-transparent text-center">
          <q-card-section>
            <div class="text-h3 text-weight-bold section-heading">Interior</div>
            <div class="text-h6 text-weight-thin">
              Make your home more minimized
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>

    <div class="diagonal-box ">
      <div class="container q-py-xl">
        <div class="text-center q-pa-xl">
          <div class="text-h4 text-weight-bold section-heading">SHOP</div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-6 col-md-4" v-for="product in products" :key="product.id">
            <q-card flat class="q-ma-md">
              <img
                :src="product.imageSrc"
                style="height:350px"
              />
              <q-card-section class="q-px-none">
                <div class="text-h6">{{ product.name }}</div>
                <div class="text-subtitle2">${{product.price}}</div>
              </q-card-section>
            </q-card>
          </div>
        </div>
        <div class="text-center q-pa-lg">
          <q-btn
            outline
            color="dark"
            class="no-round"
            size="md"
            label="ALL PRODUCTS"
          />
        </div>
      </div>
    </div>

    <div class="diagonal-box ">
      <div class="container q-py-xl">
        <div class="text-center q-pa-xl">
          <div class="text-h4 text-weight-bold section-heading">PROJECTS</div>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-6 col-md-4" v-for="project in projects" :key="project.id">
            <q-card flat class="q-ma-md">
              <img
                :src="project.imageSrc"
                style="height:350px"
              />
            </q-card>
          </div>
        </div>
       
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "PageIndex",
  data() {
    return {
      products: [
        {
          id: "1",
          name: "Simple Shelf",
          imageSrc: require("src/assets/interiorDesignProducts/shelf.jpg"),
          price: "60"
        },
        {
          id: "2",
          name: "Mini Sofa",
          imageSrc: require("src/assets/interiorDesignProducts/sofa.jpg"),
          price: "78"
        },
        {
          id: "3",
          name: "Study Lamp",
          imageSrc: require("src/assets/interiorDesignProducts/lamp.jpg"),
          price: "84"
        },
        {
          id: "4",
          name: "Mini Chair",
          imageSrc: require("src/assets/interiorDesignProducts/chair.jpg"),
          price: "58"
        },
        {
          id: "5",
          name: "Simple Table",
          imageSrc: require("src/assets/interiorDesignProducts/table2.jpg"),
          price: "66"
        },
        {
          id: "6",
          name: "Table Top",
          imageSrc: require("src/assets/interiorDesignProducts/tabletop.jpg"),
          price: "90"
        }
      ],
      projects: [
        {
          id: "1",
          imageSrc: require("src/assets/interiorDesignProducts/proj1.jpg")
        },
        {
          id: "2",
          imageSrc: require("src/assets/interiorDesignProducts/proj2.jpg")
        },
        {
          id: "3",
          imageSrc: require("src/assets/interiorDesignProducts/proj3.jpg")
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.section-heading {
  letter-spacing: 2px;
}
</style>
