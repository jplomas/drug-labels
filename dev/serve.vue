<script setup>
import { defineComponent, ref } from "vue";
import DrugLabel from "@/drug-label.vue";

const selectedType = ref('others');
const bordered = ref(true);
const scaled = ref(true);
const size = ref('normal');
const name = ref('teicoplanin');
const concentration = ref('40');
const units = ref('mg/ml');

defineComponent({
  name: "ServeDev",
  components: {
    DrugLabel,
  },
});
</script>

<template>
  <div id="app">
    <h1>Playground</h1>
    <h3>Parameters</h3>
    <form>
      <select v-model="selectedType">
        <option
          disabled
          value=""
        >
          Please select one
        </option>
        <option>others</option>
        <option>local-anaesthetic</option>
        <option>induction-agent</option>
        <option>hypnotic</option>
        <option>hypnotic-antagonist</option>
        <option>antiemetic</option>
        <option>neuromuscular-blocker-antagonist</option>
        <option>neuromuscular-blocker</option>
        <option>depolarizing-neuromuscular-blocker</option>
        <option>opioid</option>
        <option>opioid-antagonist</option>
        <option>vasopressor</option>
        <option>anticholinergic</option>
        <option>adrenaline</option>
        <option>hypotensive</option>
      </select>
      <p>
        Bordered:
        <input
          v-model="bordered"
          type="radio"
          value="true"
        >
        <label>True</label>

        <input
          v-model="bordered"
          type="radio"
          value="false"
        >
        <label>False</label>
      </p>
      <p>
        Scaled:
        <input
          v-model="scaled"
          type="radio"
          value="true"
        >
        <label>True</label>

        <input
          v-model="scaled"
          type="radio"
          value="false"
        >
        <label>False</label>
      </p>
      <select v-model="size">
        <option>normal</option>
        <option>small</option>
        <option>xsmall</option>
      </select>
      <p>
        Name:
        <input
          v-model="name"
          type="text"
        >
      </p>
      <p>
        Concentration:
        <input
          v-model="concentration"
          type="text"
        >
      </p>
      <p>
        Units:
        <input
          v-model="units"
          type="text"
        >
      </p>
    </form>
    <h3>Result</h3>
    <drug-label
      :type="selectedType"
      :name="name"
      :concentration="concentration"
      :units="units"
      :bordered="bordered"
      :size="size"
      :scaled="scaled"
    />

    <hr>
    <drug-label
      name="Midazolam"
      type="hypnotic"
      scaled
    />
    <p />
    <drug-label
      name="Midazolam"
      type="hypnotic"
      scaled
      size="small"
    />
    <p />
    <drug-label
      name="Midazolam"
      type="hypnotic"
      scaled
      size="xsmall"
    />
    <p />
    <div style="width: 500px">
      <drug-label
        scaled
        bordered
      />
    </div>
    <div style="width: 300px">
      <drug-label type="induction-agent" />
    </div>
    <div style="width: 100%">
      <drug-label
        type="foo"
        bordered
        scaled
        size="small"
      />
      <drug-label
        type="foo"
        bordered
        scaled
        size="xsmall"
      />
      <drug-label
        type="foo"
        bordered
        scaled
      />
      <drug-label
        type="hypnotic"
        bordered
        scaled
      />
      <drug-label
        name="Midazolam"
        type="hypnotic"
        scaled
      />
      <drug-label
        name="Midazolam"
        type="hypnotic"
        scaled
        size="small"
      />
      <drug-label
        name="Midazolam"
        type="hypnotic"
        scaled
        size="xsmall"
      />
      <drug-label
        type="induction-agent"
        name="propofol"
        units="mcg/ml"
        scaled
      />
      <drug-label
        type="local-anaesthetic"
        name="lignocaine"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="adrenaline"
        name="Adrenaline 1:1000"
        units="mcg/ml"
        scaled
      />
      <drug-label
        type="adrenaline"
        name="Adrenaline 1:1000"
        units="mcg/ml"
        scaled
        size="small"
      />
      <drug-label
        type="adrenaline"
        name="Adrenaline 1:1000"
        units="mcg/ml"
        scaled
        size="xsmall"
      />
      <drug-label
        type="antiemetic"
        name="cyclizine"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="hypotensive"
        name="labetalol"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="neuromuscular-blocker"
        name="atracurium"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="neuromuscular-blocker-antagonist"
        name="Neostigmine/Glycopyrrolate"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="depolarizing-neuromuscular-blocker"
        name="suxamethonium"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="hypnotic-antagonist"
        name="flumazanil"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="opioid"
        name="fentanyl"
        units="mg/ml"
        scaled
      />
      <drug-label
        type="opioid-antagonist"
        name="naloxone"
        units="mg/ml"
        bordered
        scaled
      />
      <drug-label
        type="opioid-antagonist"
        name="naloxone"
        units="mg/ml"
        bordered
        scaled
        size="small"
      />
      <drug-label
        type="opioid-antagonist"
        name="naloxone"
        units="mg/ml"
        bordered
        scaled
        size="xsmall"
      />
      <drug-label
        type="vasopressor"
        name="metaraminol"
        units="mg/ml"
        bordered
        scaled
      />
      <drug-label
        type="anticholinergic"
        name="atropine"
        units="mcg/ml"
        bordered
        scaled
      />
    </div>
  </div>
</template>
<style scoped>
/* .drug-label {
  height: 4rem;
} */
</style>
