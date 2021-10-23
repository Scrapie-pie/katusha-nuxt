<template>
  <section class="section-models">
    <h1>Линейка печатной техники «Катюша»</h1>
    <div class="blocks">
      <BlockModelsSlider :models="models"/>
      <BlockModelsAll :models="models"/>
      <BlockDistributors/>
    </div>

  </section>
</template>

<script>
export default {
  name: 'SectionModels',
  data: () => ({
    models: [
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
      {
        name: 'МФУ «Катюша»',
        alias: 'M247',
        description: 'Компактное, производительное многофункциональное устройство печати для малого и среднего офиса',
        caption: 'Высокая производительность, двусторонняя печать, цветной сканер, однопроходный автоподатчик оригиналов, сканирование формата А3',
        image: require('@/src/images/models/model01.png'),
        labels: {
          print: {
            icon: 'print',
            name: 'Скорость печати',
            value: '47 страниц в минуту'
          },
          resolution: {
            icon: 'image',
            name: 'Разрешение',
            value: '1200x1200 dpi'
          },
          format: {
            icon: 'layers',
            name: 'Сканирование форматов',
            value: 'А3'
          },
        }
      },
    ]
  }),
}

</script>

<style lang="scss">
.section-models {
  .banner {
    background-color: get-variable(color, grey);
    position: relative;
  }
}
</style>
