<template>
  <oh-list-item :context="context" class="input-listitem">
    <div slot="footer">
      <generic-widget-component :context="childContext(afterComponent)" v-on="$listeners" />
    </div>
  </oh-list-item>
</template>

<style lang="stylus">
.input-listitem
  .item-title
    width 100%
    .item-footer
      height inherit
</style>

<script>
import mixin from '../../widget-mixin'
import OhListItem from './oh-list-item.vue'
import { OhInputItemDefinition } from '@/assets/definitions/widgets/standard/listitems'

export default {
  components: {
    OhListItem
  },
  mixins: [mixin],
  widget: OhInputItemDefinition,
  computed: {
    afterComponent () {
      return {
        component: 'oh-input',
        config: this.config
      }
    }
  }
}
</script>
