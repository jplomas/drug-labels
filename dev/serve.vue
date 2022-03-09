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
      <drug-label
        type="local-anaesthetic"
        name="lignocaine"
        units="mg/ml"
      />
      <drug-label
        type="antiemetic"
        name="cyclizine"
        units="mg/ml"
      />
      <drug-label
        type="neuromuscular-blocker"
        name="atracurium"
        units="mg/ml"
      />
      <drug-label
        type="neuromuscular-blocker-antagonist"
        name="Neostigmine/Glycopyrrolate"
        units="mg/ml"
      />
      <drug-label
        type="depolarizing-neuromuscular-blocker"
        name="suxamethonium"
        units="mg/ml"
      />
      <drug-label
        type="opioid"
        name="fentanyl"
        units="mg/ml"
      />
      <drug-label
        type="opioid-antagonist"
        name="naloxone"
        units="mg/ml"
        bordered
      />
      <!--
          'local-anaesthetic',
          'induction-agent',
          'hypnotic',
          'hypnotic-antagonist',
          'antiemetic',
          'neuromuscular-blocker-antagonist',
          'neuromuscular-blocker',
          'depolarizing-neuromuscular-blocker'
        -->
    </div>
  </div>
</template>
