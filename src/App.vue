<template>
  <div style="flex-direction: column;">
    <Header />
    <Content :planet="selectedPlanet"/>
    <TableInfo :planet="selectedPlanet"/>
  </div>
  
</template>

<script>
import Header from './components/Header.vue';
import Content from './components/Content.vue';
import TableInfo from './components/TableInfo.vue';

export default {
  name: 'PlanetsApp',
  components:{
    Header,
    Content,
    TableInfo
  },
  data () {
    return {
      solarSistem: {
        mercury: {
          name: 'mercury',
          overview: 'Mercúrio é o menor planeta do Sistema Solar e o mais próximo do Sol. Sua órbita ao redor do Sol leva 87,97 dias terrestres, o mais curto de todos os planetas do Sol. Mercúrio é um dos quatro planetas terrestres do Sistema Solar, e é um corpo rochoso como a Terra.',
          internalStructure: 'O mercúrio parece ter uma crosta sólida de silicato e manto sobrejacente a uma camada de núcleo externo sólido de sulfeto de ferro, uma camada de núcleo líquido mais profunda e um núcleo interno sólido. A densidade do planeta é a segunda mais alta do Sistema Solar, com 5.427 g/cm3, apenas um pouco menor do que a densidade da Terra.',
          surfaceGeology: 'A superfície de Mercúrio é semelhante em aparência à da Lua, mostrando extensas planícies semelhantes a mares e crateras pesadas, indicando que ele tem sido geologicamente inativo por bilhões de anos. É mais heterogêneo do que o de Marte ou da Lua.',
          rotationTime: '58,6 Dias',
          revolutionTime: '87,97 Dias',
          radius: '2.439,7 km',
          averageTemp: '430°c',
          image1: 'mercury1.svg',
          image2: 'mercury2.svg',
          image3: 'mercury3.svg',
          link: 'https://pt.wikipedia.org/wiki/Merc%C3%BArio_(planeta)',
          color: '#419EBB'
        }
      },
      selectedPlanet: {}
    }
  },
  created () { this.selectedPlanet = this.solarSistem.mercury }
}
</script>

<style>
  body {
   margin: 0px;
   background-image: url('./assets/background.svg');
   font-family: 'Spartan';
  }
  div {
    display: flex;
    align-items: center;
  }
  p {font-family: 'Spartan';}
</style>
