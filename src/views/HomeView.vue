<script>
import mainComp from "@/components/mainComp.vue";
import descComp from '@/components/descComp.vue';
import categoryComp from '@/components/categoryComp.vue';
import Adverts from "@/components/Adverts.vue";
import collection from "@/components/collection.vue";
import HotDeal from "@/components/HotDeal.vue";
import Newsletter from "@/components/Newsletter.vue";
import FooterComp from "@/components/FooterComp.vue";
export default{
    components: { mainComp, 
        descComp, 
        categoryComp, 
        Adverts, 
        collection, 
        HotDeal, 
        Newsletter, 
        FooterComp  },
    }


</script>

<template>
<main-comp/>
<desc-comp/>
<category-comp/>
<adverts/>
<collection/>
<hot-deal/>
<newsletter/>
<footer-comp/>
</template>
