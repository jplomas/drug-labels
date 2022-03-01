<script>
import { defineComponent } from 'vue';
import DrugLabel from '@/drug-label.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    DrugLabel
  }
});
</script>

<template>
  <div id="app">
    <div style="width: 500px;">
      <drug-label
        class="scaled"
      />
    </div>
    <div style="width: 300px;">
      <drug-label type="induction-agent" />
    </div>
    <div style="width: 400px;">
      <drug-label
        name="Midazolam"
        type="hypnotic"
      />
      <drug-label
        type="foo"
        bordered
      />
      <drug-label
        type="hypnotic"
        bordered
      />
      <drug-label
        type="induction-agent"
        name="propofol"
        units="mcg/ml"
      />
    </div>
  </div>
</template>
