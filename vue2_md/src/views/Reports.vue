<template>
  <div class="home">
    <ReportsComponent/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ReportsComponent from '@/components/ReportsComponent.vue';

@Component({
  components: {
    ReportsComponent,
  },
})
export default class Reports extends Vue {}
</script>
