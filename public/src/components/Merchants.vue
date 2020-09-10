<template>
  <el-row>
    <el-col :span="16" :offset="4">
      <div class="merchants-container">
        <el-card class="box-card" body-style="padding: 0px;">
          <el-row>
            <el-col :span="6" class="merchants-category">
              <app-merchant-category></app-merchant-category>
            </el-col>
            <el-col :span="18" class="merchants">
              <app-merchant-detail :merchant="selectedMerchant"></app-merchant-detail>
            </el-col>
          </el-row>
        </el-card>
      </div>
    </el-col>
  </el-row>
</template>

<script>
  import MerchantCategory from './MerchantCategory'
  import MerchantDetail from './MerchantDetail'
  import { eventBus } from '../main';

  import imgDDJ400 from '../assets/merchants/ddj400.jpg'

  export default {
    components: {
      appMerchantCategory: MerchantCategory,
      appMerchantDetail: MerchantDetail,
    },
    data() {
      return {
        merchants: [
          {
            category: 'DJ Controller',
            title: 'Pioneer DJ DDJ 400',
            description: 'An entry level DJ controller with all the features you need including jogwheel with vinyl mode and eight performance pads.',
            img: 'https://m.media-amazon.com/images/S/aplus-media/vc/22b644ad-298d-4220-b605-242e6233c014.__CR0,0,970,600_PT0_SX970_V1___.jpg'
          },
          {
            category: 'Standalone DJ System',
            title: 'Denon DJ Prime 4',
            description: 'This standalone DJ system is absolutely a powerhouse for professional mobile DJs and Club DJs.',
            img: 'https://media.sweetwater.com/images/items/750/Prime4-large.jpg?v=5de0cece0f5766c4'
          },
          {
            category: 'Flight Case',
            title: 'Odessy Filght Case',
            description: 'This flight case is for Denon DJ Prime 4 DJ system. It is built to last and can stand long distance trips by flight and ground transport.',
            img: 'https://www.agiprodj.com/additional_images/odyssey-frprime4bl-front.jpg'
          },
          {
            category: 'Headphones',
            title: 'Sennheiser HD 25',
            description: 'The Sennheiser HD 25 is a great headphone for both on stage and studio environment. It has prestine sound quality for all ranges and is built to endure the harsh environment of stage performance.',
            img: 'https://specials-images.forbesimg.com/imageserve/5ee18c0c194e4200062e8f9d/960x0.jpg'
          },
          {
            category: 'Speakers',
            title: 'KRK Rokit 5 Gen 4',
            description: 'The newest generation of the classic Rokit 5 series. This pair of 5 inch powered studio monitors is ideal for music production and DJ monitoring. ',
            img: 'https://cdn11.bigcommerce.com/s-7i8y5wa/images/stencil/1280x1280/products/32164/921065/KRK-RP5G4-NA-COMBO-STD-2__94160.1585616778.jpg?c=2&imbypass=on'
          },
        ],
        selectedMerchant: {
            category: 'DJ Controller',
            title: 'Pioneer DJ DDJ 400',
            description: 'An entry level DJ controller with all the features you need including jogwheel with vinyl mode and eight performance pads.',
            img: 'https://m.media-amazon.com/images/S/aplus-media/vc/22b644ad-298d-4220-b605-242e6233c014.__CR0,0,970,600_PT0_SX970_V1___.jpg'
          },
      }
    },
    created() {
      eventBus.$on('selectedCategory', (data) => {
        for (const merchant of this.merchants) {
          if (merchant.category == data) {
            this.selectedMerchant = merchant;
          }
        }
      });
    }
  }
</script>

<style scoped>
  .merchants-container {
    margin-top: 25vh;
    margin-bottom: 150px;
    height: 38vh;
  }

</style>