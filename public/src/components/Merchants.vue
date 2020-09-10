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
            img: 'https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07F3TNCMK&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL500_&tag=djjyugstore-20',
            link: 'https://www.amazon.com/gp/product/B07F3TNCMK/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07F3TNCMK&linkCode=as2&tag=djjyugstore-20&linkId=e2f16d232ba7de92435d03ae3ab989b4'
          },
          {
            category: 'Standalone DJ System',
            title: 'Denon DJ Prime 4',
            description: 'This standalone DJ system is absolutely a powerhouse for professional mobile DJs and Club DJs.',
            img: 'https://media.sweetwater.com/images/items/750/Prime4-large.jpg?v=5de0cece0f5766c4',
            link: 'https://www.amazon.com/gp/product/B07MGJGPMM/ref=as_li_tl?ie=UTF8&tag=djjyugstore-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B07MGJGPMM&linkId=6f8096959412d72f176b85fa0a95c7c3'
          },
          {
            category: 'Flight Case',
            title: 'Odessy Filght Case',
            description: 'This flight case is for Denon DJ Prime 4 DJ system. It is built to last and can stand long distance trips by flight and ground transport.',
            img: 'https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07ZQT47M1&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL500_&tag=djjyugstore-20',
            link: 'https://www.amazon.com/gp/product/B07ZQT47M1/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07ZQT47M1&linkCode=as2&tag=djjyugstore-20&linkId=23d3e3a78813cdf006e080151e45c51c'
          },
          {
            category: 'Headphones',
            title: 'Sennheiser HD 25',
            description: 'The Sennheiser HD 25 is a great headphone for both on stage and studio environment. It has prestine sound quality for all ranges and is built to endure the harsh environment of stage performance.',
            img: 'https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B01CRI3UOU&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL500_&tag=djjyugstore-20',
            link: 'https://www.amazon.com/gp/product/B01CRI3UOU/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B01CRI3UOU&linkCode=as2&tag=djjyugstore-20&linkId=d7a9a797f32be949a18e3b316e9a5aa2'
          },
          {
            category: 'Speakers',
            title: 'KRK Rokit 5 Gen 4',
            description: 'The newest generation of the classic Rokit 5 series. This pair of 5 inch powered studio monitors is ideal for music production and DJ monitoring. ',
            img: 'https://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07TJS993L&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL250_&tag=djjyugstore-20" ',
            link: 'https://www.amazon.com/gp/product/B07TJS993L/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07TJS993L&linkCode=as2&tag=djjyugstore-20&linkId=2d7891ea2a01e1a4212f45260df364fe'
          },
        ],
        selectedMerchant: {
            category: 'DJ Controller',
            title: 'Pioneer DJ DDJ 400',
            description: 'An entry level DJ controller with all the features you need including jogwheel with vinyl mode and eight performance pads.',
            img: 'https://m.media-amazon.com/images/S/aplus-media/vc/22b644ad-298d-4220-b605-242e6233c014.__CR0,0,970,600_PT0_SX970_V1___.jpg',
            link: 'https://www.amazon.com/gp/product/B07F3TNCMK/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07F3TNCMK&linkCode=as2&tag=djjyugstore-20&linkId=e2f16d232ba7de92435d03ae3ab989b4'
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