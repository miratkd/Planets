<template>
  <div style="flex-direction: column;">
    <Header :setPlanet="setPlanet" :solarSistem="solarSistem"/>
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
          name: 'Mercúrio',
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
        },
        venus: {
          name: 'Vênus',
          overview: 'Vênus é o segundo planeta a partir do Sol. É nomeado após a deusa romana do amor e da beleza. Como o objeto natural mais brilhante no céu noturno da Terra depois da Lua, Vênus pode projetar sombras e pode ser, em raras ocasiões, visível a olho nu em plena luz do dia.',
          internalStructure: 'A semelhança de tamanho e densidade entre Vênus e a Terra sugere que eles compartilham uma estrutura interna semelhante: um núcleo, manto e crosta. Como o da Terra, o núcleo venusiano é provavelmente pelo menos parcialmente líquido porque os dois planetas estão esfriando aproximadamente na mesma taxa.',
          surfaceGeology: 'Grande parte da superfície venusiana parece ter sido moldada pela atividade vulcânica. Vênus tem várias vezes mais vulcões do que a Terra, e tem 167 grandes vulcões que têm mais de 100 km (60 milhas) de diâmetro. O único complexo vulcânico desse tamanho na Terra é a Ilha Grande do Havaí.',
          rotationTime: '243 Dias',
          revolutionTime: '224,7 Dias',
          radius: '6.051,8 km',
          averageTemp: '471°c',
          image1: 'venus1.svg',
          image2: 'venus2.svg',
          image3: 'venus3.svg',
          link: 'https://pt.wikipedia.org/wiki/V%C3%A9nus_(planeta)',
          color: '#EDA249'
        },
        earth: {
          name: 'Terra',
          overview: 'Terceiro planeta do Sol e o único planeta conhecido a abrigar vida. Cerca de 29,2% da superfície da Terra é terra, com os restantes 70,8% cobertos de água. A distância da Terra do Sol, as propriedades físicas e a história geológica permitiram que a vida evoluísse e prosperasse.',
          internalStructure: 'O interior da Terra, como o dos outros planetas terrestres, é dividido em camadas por suas propriedades químicas ou físicas (reológicas). A camada externa é uma crosta sólida de silicato quimicamente distinta, que é sustentada por um manto sólido altamente viscoso.',
          surfaceGeology: 'A área total da superfície da Terra é de cerca de 510 milhões de km2. A crosta continental consiste em material de baixa densidade, como as rochas ígneas granito e andesito. Menos comum é o basalto, uma rocha vulcânica mais densa que é o principal constituinte do fundo do oceano.',
          rotationTime: '1 Dia',
          revolutionTime: '365,26 Dias',
          radius: '6.371 km',
          averageTemp: '16°c',
          image1: 'terra1.svg',
          image2: 'terra2.svg',
          image3: 'terra3.svg',
          link: 'https://pt.wikipedia.org/wiki/Terra',
          color: '#6D2ED5'
        },
        mars: {
          name: 'Marte',
          overview: 'Marte é o quarto planeta a partir do Sol e o segundo menor planeta do Sistema Solar, sendo maior do que apenas Mercúrio. Em inglês, Marte carrega o nome do deus romano da guerra e é muitas vezes referido como o "Planeta Vermelho".',
          internalStructure: 'Como a Terra, Marte se diferenciou em um núcleo metálico denso sobreposto por materiais menos densos. Os cientistas inicialmente determinaram que o núcleo é pelo menos parcialmente líquido. Os modelos atuais de seu interior implicam um núcleo consistindo principalmente de ferro e níquel com cerca de 16-17% de enxofre.',
          surfaceGeology: 'Marte é um planeta terrestre cuja superfície consiste em minerais contendo silício e oxigênio, metais e outros elementos que normalmente compõem a rocha. A superfície é composta principalmente de basalto toleiítico, embora as partes sejam mais ricas em sílica do que o basalto típico.',
          rotationTime: '1,03 Dias',
          revolutionTime: '1,88 Anos',
          radius: '3.389,5 km',
          averageTemp: '-28°c',
          image1: 'mars1.svg',
          image2: 'mars2.svg',
          image3: 'mars3.svg',
          link: 'https://es.wikipedia.org/wiki/Marte_(planeta)#:~:text=Marte%20es%20el%20planeta%20interior%20m%C3%A1s%20alejado%20del,7%20%E2%80%8B%20similares%20al%20asteroide%20troyano%20%285261%29%20Eureka.',
          color: '#D14C32'
        },
        jupiter: {
          name: 'Júpiter',
          overview: 'Júpiter é o quinto planeta a partir do Sol e o maior do Sistema Solar. É um gigante gasoso com uma massa duas vezes e meia maior que a de todos os outros planetas do Sistema Solar combinados, mas menos de um milésimo da massa do Sol.',
          internalStructure: 'Quando a Juno chegou em 2016, descobriu que Júpiter tem um núcleo muito difuso que se mistura em seu manto. Uma possível causa é um impacto de um planeta de cerca de dez massas terrestres alguns milhões de anos após a formação de Júpiter, o que teria perturbado um núcleo joviano originalmente sólido.',
          surfaceGeology: 'A característica mais conhecida de Júpiter é a Grande Mancha Vermelha, uma tempestade anticiclônica persistente localizada a 22° ao sul do equador. Sabe-se que existe desde pelo menos 1831 e, possivelmente, desde 1665.',
          rotationTime: '9,93 Horas',
          revolutionTime: '11,86 Anos',
          radius: '69.911 km',
          averageTemp: '-108°c',
          image1: 'jupiter1.svg',
          image2: 'jupiter2.svg',
          image3: 'jupiter3.svg',
          link: 'https://pt.wikipedia.org/wiki/J%C3%BApiter_(planeta)#:~:text=J%C3%BApiter%20%28planeta%29%20J%C3%BApiter%20%C3%A9%20o%20maior%20planeta%20do,planeta%20gasoso%2C%20junto%20com%20Saturno%2C%20Urano%20e%20Netuno.',
          color: '#D83A34'
        },
        saturn: {
          name: 'Saturno',
          overview: 'Saturno é o sexto planeta a partir do Sol e o segundo maior do Sistema Solar, depois de Júpiter. É um gigante gasoso com um raio médio de cerca de nove vezes e meia o da Terra. Tem apenas um oitavo da densidade média da Terra.',
          internalStructure: 'Apesar de consistir principalmente de hidrogênio e hélio, a maior parte da massa de Saturno não está na fase gasosa, porque o hidrogênio se torna um líquido não ideal quando a densidade está acima de 0,01 g / cm3, que é alcançada em um raio contendo 99,9% da massa de Saturno.',
          surfaceGeology: 'A atmosfera externa de Saturno contém 96,3% de hidrogênio molecular e 3,25% de hélio em volume. A característica mais famosa do planeta é o seu proeminente sistema de anéis, que é composto principalmente de partículas de gelo com uma quantidade menor de detritos rochosos e poeira. ',
          rotationTime: '10,8 Horas',
          revolutionTime: '29,46 Anos',
          radius: '58.232 km',
          averageTemp: '-138°c',
          image1: 'saturn1.svg',
          image2: 'saturn2.svg',
          image3: 'saturn3.svg',
          link: 'https://pt.wikipedia.org/wiki/Saturno_(planeta)',
          color: '#CD5120'
        },
        uranus: {
          name: 'Urano',
          overview: 'Urano é o sétimo planeta a partir do Sol. Seu nome é uma referência ao deus grego do céu, Urano de acordo com a mitologia grega, foi o bisavô de Ares. Tem o terceiro maior raio planetário e a quarta maior massa planetária do Sistema Solar.',
          internalStructure: 'O modelo padrão da estrutura de Urano é que ele consiste em três camadas: um núcleo rochoso (silicato / ferro-níquel) no centro, um manto gelado no meio e um envelope externo de hidrogênio gasoso / hélio. O núcleo é relativamente pequeno, com uma massa de apenas 0,55 massas terrestres.',
          surfaceGeology: 'A composição da atmosfera de Urano é diferente de seu volume, consistindo principalmente de hidrogênio molecular e hélio. A fração molar de hélio, ou seja, o número de átomos de hélio por molécula de gás, é de 0,15±0,03 na troposfera superior.',
          rotationTime: '17,2 Horas',
          revolutionTime: '84 Anos',
          radius: '25.362 km',
          averageTemp: '-195°c',
          image1: 'uranus1.svg',
          image2: 'uranus2.svg',
          image3: 'uranus3.svg',
          link: 'https://pt.wikipedia.org/wiki/Urano_(planeta)#:~:text=Urano%20%28planeta%29%20Origem%3A%20Wikip%C3%A9dia%2C%20a%20enciclop%C3%A9dia%20livre.%20Nota%3A,homenagem%20ao%20deus%20grego%20do%20c%C3%A9u%2C%20Urano%2C%20',
          color: '#1EC1A2'
        },
        neptune: {
          name: 'Netuno',
          overview: 'Netuno é o oitavo e mais distante planeta solar conhecido do Sol. No Sistema Solar, é o quarto maior planeta em diâmetro, o terceiro planeta mais massivo e o planeta gigante mais denso. Tem 17 vezes a massa da Terra, mais massiva do que o seu quase gémeo Urano.',
          internalStructure: 'A estrutura interna de Netuno se assemelha à de Urano. Sua atmosfera forma cerca de 5% a 10% de sua massa e se estende talvez de 10% a 20% do caminho em direção ao núcleo. Concentrações crescentes de metano, amônia e água são encontradas nas regiões mais baixas.',
          surfaceGeology: 'A atmosfera de Netuno é de 80% de hidrogênio e 19% de hélio. Uma quantidade vestigiada de metano também está presente. Bandas de absorção proeminentes de metano existem em comprimentos de onda acima de 600 nm, na porção vermelha e infravermelha do espectro.',
          rotationTime: '16,08 Horas',
          revolutionTime: '164,79 Anos',
          radius: '24.622 km',
          averageTemp: '-201°c',
          image1: 'neptune1.svg',
          image2: 'neptune2.svg',
          image3: 'neptune3.svg',
          link: 'https://pt.wikipedia.org/wiki/Netuno_(planeta)#:~:text=Netuno%20orbita%20o%20Sol%20a%20uma%20dist%C3%A2ncia%20m%C3%A9dia,turbulenta%20atmosfera%2C%20constitu%C3%ADda%20predominantemente%20de%20hidrog%C3%AAnio%20e%20h%C3%A9lio.',
          color: '#2D68F0'
        },
      },
      selectedPlanet: {}
    }
  },
  created () { this.selectedPlanet = this.solarSistem.mercury },
  methods: {
    setPlanet (planet) { this.selectedPlanet = planet }
  }
}
</script>

<style>
  body {
   margin: 0px;
   background-image: url('./assets/background.svg');
   overflow-x: hidden;
   font-family: 'Spartan';
  }
  div {
    display: flex;
    align-items: center;
  }
  p {font-family: 'Spartan';}
</style>
