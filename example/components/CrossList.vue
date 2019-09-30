<template>
  <ComponentExample link="CrossList">
    <div class="side-by-side">
      <div class="side">
        <VueNestable
          v-model="nestableItems1"
          cross-list
          group="cross"
        >
          <VueNestableHandle
            slot-scope="{ item }"
            :item="item"
          >
            {{ item.text }}
          </VueNestableHandle>
        </VueNestable>
      </div>
      <div class="side">
        <VueNestable
          v-model="nestableItems2"
          cross-list
          group="cross"
        >
          <VueNestableHandle
            slot-scope="{ item }"
            :item="item"
          >
            {{ item.text }}
          </VueNestableHandle>
        </VueNestable>
      </div>
    </div>
  </ComponentExample>
</template>

<script>
import ComponentExample from './ComponentExample.vue'

export default {
  components: {
    ComponentExample
  },

  data () {
    return {
      nestableItems1: [
        {
          id: 0,
          text: 'Greet'
        }, {
          id: 1,
          text: 'AskPhoneNumber',
          children: [{
            id: 2,
            text: 'AskAddress'
          }]
        }, {
          id: 3,
          text: 'Thanks'
        }
      ],
      nestableItems2: [
        {
          id: 4,
          text: 'OrderFlight'
        }, {
          id: 5,
          text: 'OrderHotel'
        }
      ]
    }
  }
}
</script>

<style scoped>
</style>
