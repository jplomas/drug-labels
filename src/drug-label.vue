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
          'hypnotic',
          'hypnotic-antagonist',
          'antiemetic',
          'neuromuscular-blocker-antagonist',
          'neuromuscular-blocker',
          'depolarizing-neuromuscular-blocker',
          'opioid',
          'opioid-antagonist',
          'vasopressor',
          'anticholinergic',
          'adrenaline',
          'hypotensive',
        ];
        if (drugs.includes(this.$attrs.type.toLowerCase())) {
          cssClass = this.$attrs.type.toLowerCase();
        }
      }
      if (this.$attrs.bordered !== undefined) {
        cssClass += ' bordered';
      }
      if (this.$attrs.scaled !== undefined) {
        cssClass += ' scaled';
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
    <p class="top">
      <strong>{{ name }}</strong>
    </p>
    <p class="bottom">
      <span>{{ concentration }} {{ units }}</span>
    </p>
  </div>
</template>

<style> /* eslint-disable-line */
.drug-label {
  box-sizing: border-box;
  width: 100%;
  padding: 0.4rem;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.1rem;
  text-align: center;
  border-radius: 1rem;
}
.drug-label .top {
  padding-top: 0.1rem;
  margin-top: 0.4rem;
  margin-bottom: 0.6rem;
  padding-bottom: 0.1rem;
}
.drug-label .bottom {
  margin-bottom: 0.1rem;
  padding-bottom: 0.6rem;
  margin-top: 0.1rem;
  padding-bottom: 0.2rem;
}
.scaled {
  width: 16rem;
}

.local-anaesthetic {
  background-color: #afa9a0;
}

.induction-agent {
  background-color: #ffe800;
}

.hypnotic {
  background-color: #ff8200;
}
.hypnotic-antagonist {
  background: repeating-linear-gradient(
    -45deg,
    #ff8200,
    #ff8200 0.5rem,
    #ffffff 0.5rem,
    #ffffff 1rem
  );
}
.hypnotic-antagonist .top strong,
.hypnotic-antagonist .bottom span {
  background: #ffffff;
  padding: 0.2rem;
}
.hypotensive {
  background: repeating-linear-gradient(
    -45deg,
    #d6bfdd,
    #d6bfdd 0.5rem,
    #ffffff 0.5rem,
    #ffffff 1rem
  );
}
.hypotensive .top strong,
.hypotensive .bottom span {
  background: #ffffff;
  padding: 0.2rem;
}
.neuromuscular-blocker {
  background-color: #ff7477;
}
.neuromuscular-blocker-antagonist {
  background: repeating-linear-gradient(
    -45deg,
    #ff7477,
    #ff7477 0.5rem,
    #ffffff 0.5rem,
    #ffffff 1rem
  );
}
.neuromuscular-blocker-antagonist .top strong,
.neuromuscular-blocker-antagonist .bottom span {
  background: #ffffff;
  padding: 0.2rem;
}
.depolarizing-neuromuscular-blocker {
  background-color: #ff7477;
  background: linear-gradient(#000000 50%, #ff7477 50%);
  padding-top: 0.1rem;
}
.depolarizing-neuromuscular-blocker .top {
  color: #ff7477;
  padding-top: 0rem;
}
.depolarizing-neuromuscular-blocker .bottom {
  padding-top: 0.3rem;
}
.antiemetic {
  background-color: #efbe7d;
}
.opioid {
  background-color: #71c5e8;
}

.opioid-antagonist {
  background: repeating-linear-gradient(
    -45deg,
    #71c5e8,
    #71c5e8 0.5rem,
    #ffffff 0.5rem,
    #ffffff 1rem
  );
}
.opioid-antagonist .top strong,
.opioid-antagonist .bottom span {
  background: #ffffff;
  padding: 0.2rem;
}
.vasopressor {
  background-color: #d6bfdd;
}
.anticholinergic {
  background-color: #a4d65e;
}
.adrenaline {
  background-color: #000000;
  background: linear-gradient(#000000 50%, #d6bfdd 50%);
  padding-top: 0.1rem;
}
.adrenaline .top {
  color: #d6bfdd;
  padding-top: 0rem;
}
.adrenaline .bottom {
  background-color: #d6bfdd;
  padding-top: 0.3rem;
}
.others {
  background-color: #ffffff;
}
.bordered {
  border: 1px solid #000000;
}
</style>
