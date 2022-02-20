<template  >
<div  class="bg-image d-flex justify-content-center align-items-center"
     style="
            background-image: url('https://images7.alphacoders.com/992/thumb-1920-992404.jpg');
            height: 100%
            
            
            
            " >
  <v-container >
    
    <center><h1 class="text-info">Product Page</h1></center>
    <v-container class="d-flex flex-wrap">
      <v-card
        class="mx-auto mb-5"
        max-width="400"
        v-for="(i, index) in productlist"
        :key="index"
      >
        <v-img class="white--text align-end" height="200px" :src="i.imageurl">
          <v-card-title>{{ i.name }}</v-card-title>
        </v-img>

        <v-card-subtitle class="pb-0 ">{{ i.rightText }}</v-card-subtitle>

        <v-card-text class="text--primary">
          <div>{{ i.leftText }}</div>
        </v-card-text>

        <v-card-actions>
          <v-btn  color="info" text :to="'/detail/' + i.name">detail</v-btn>
          <v-btn color="orange" text @click="selected(i)"> Add </v-btn>
         
        </v-card-actions>
      </v-card>
    </v-container>

    <table class="table table-striped table-hover">        
    
    </table>
    <v-container
      ><h4 class="text-danger fs-1">ยอดชำระเงิน  {{ total() }} บาท</h4></v-container
    >
    <v-container grid-list-xs class="success">
      <router-view :key="$route.path"></router-view>
    </v-container>
  </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
        productlist: [
        {
         
          name: "KITO Move TwoTone AH81 (white&red)",
          imageurl:
            "https://www.kito.co.th/wp-content/uploads/2020/09/Kito-Move-TWOTONE-A-scaled.jpg",
          rightText: "price : 199",
          leftText: "Size : EU 31-45",
          producturl: "https://www.kito.co.th/product/move-twotone-ah81/",
          rightUrl:
            "https://www.kito.co.th/product-category/women/women-sandals/",
          ctaText: "Shop Now",
          active: false,
          price: 199,
        },

        {
         
          name: "มนุษย์ป้าข้างบ้าน ที่พร้อมจะส่องเรื่องของคุณ",
          imageurl:
            "https://www.slang-aholic.com/wp-content/uploads/2014/07/0457-716x400.jpg",
          rightText: "price : ในราคาประหยัดที่สามารถสืบข้อมูลได้ทุกเรื่อง เพียง! 3000",
          leftText: "",
          rightUrl:
            "https://www.kito.co.th/product-category/women/women-sandals/",
          ctaText: "Shop Now",
          active: false,
          price: 3000,
        },

        {
         
          name: "แตงโมลูกแดงๆ ถ้าเขียวไม่ใช่แตงโมละ! ลูกละ25 3ลูก 100! ",
          imageurl:
            "https://mpics.mgronline.com/pics/Images/564000005705101.JPEG",
          rightText: "price : 25 * 4 =100",
          leftText: "",
          producturl: "https://www.kito.co.th/product/move-twotone-ah81/",
          rightUrl:
            "https://www.kito.co.th/product-category/women/women-sandals/",
          ctaText: "Shop Now",
          active: false,
          price: 25,
        },

        {
         
          name: "ส้มไง ดูไงก็สม!! ไม่หวานแต่เปลือกขม (99) บาท ไม่รวมส่ง",
          imageurl:
            "https://res.cloudinary.com/dk0z4ums3/image/upload/v1500968063/attached_image_th/%25e0%25b8%25aa%25e0%25b9%2589%25e0%25b8%25a1.jpg",
          rightText: "price : 199",
          leftText: "",
          producturl: "https://www.kito.co.th/product/move-twotone-ah81/",
          rightUrl:
            "https://www.kito.co.th/product-category/women/women-sandals/",
          ctaText: "Shop Now",
          active: false,
          price: 99,
        },
      ],
    };
  },
  methods: {
    selected: function (i) {
      i.active = !i.active;
    },
    total: function () {
      var sum = 0;
      this.productlist.forEach(function (i) {
        if (i.active) {
          sum += i.price;
        }
      });
      return sum;
    },
  },
 
};
</script>

<style>
h2 {
  color: white;
}
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 100% 0%;
  }
}
h1 {
  background: linear-gradient(80deg, #0094ce, #cdeb25);
  background-size: 50%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient 2s infinite;
}
.text-danger {
  background: linear-gradient(80deg, #a71aed, #25eb46);
  background-size: 50%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient 2s infinite;
}
.white{
  background: linear-gradient(80deg, #a71aed, #25eb46);
  background-size: 50%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient 2s infinite;
}
</style>
