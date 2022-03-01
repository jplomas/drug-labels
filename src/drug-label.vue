<script lang="js">
import { defineComponent } from 'vue';

export default /*#__PURE__*/defineComponent({
  name: 'DrugLabel', // vue component name
  computed: {
    name() {
      if (this.$attrs.name !== undefined) {
        return this.$attrs.name.replace(/^\w/, c => c.toUpperCase());
      } else {
        return 'Drug';
      }
    },
    concentration() {
      if (this.$attrs.concentration !== undefined) {
        return this.$attrs.concentration;
      } else {
        return '.......................';
      }
    },
    units() {
      if (this.$attrs.units !== undefined) {
        return this.$attrs.units;
      } else {
        return 'mg/ml';
      }
    },
    type() {
      let cssClass = 'others';
      if (this.$attrs.type !== undefined) {
        let drugs = [
          'local-anaesthetic',
          'induction-agent',
          'hypnotic'
        ];
        if (drugs.includes(this.$attrs.type.toLowerCase())) {
          cssClass = this.$attrs.type.toLowerCase();
        }
      }
      if (this.$attrs.bordered !== undefined) {
        cssClass += ' bordered';
      }
      return cssClass;
    },
  },
});
</script>

<template>
  <div
    class="drug-label"
    :class="type"
  >
    <p><strong>{{ name }}</strong></p>
    <p>{{ concentration }} {{ units }}</p>
  </div>
</template>

<style scoped>
.drug-label {
    box-sizing: border-box;  
    width: 100%;
    padding: 0.5rem;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.3rem;
    text-align: center;
    border-radius: 1rem;
}

.scaled {
    width: 16rem;
}

.drug-label p {
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
}

.local-anaesthetic {
    background-color: #AFA9A0;
}

.induction-agent {
    background-color: #FFE800;
}

.hypnotic {
    background-color: #FF8200;
}
.others {
    background-color: #ffffff;
}
.bordered {
    border: 1px solid #000000;
}
</style>
