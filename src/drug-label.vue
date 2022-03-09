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
    <p class="top"><strong>{{ name }}</strong></p>
    <p class="bottom
    ">{{ concentration }} {{ units }}</p>
  </div>
</template>

<style scoped>
.drug-label {
    box-sizing: border-box;  
    width: 100%;
    padding: 0.4rem;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.2rem;
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
  padding-bottom: 0.1rem;
}
.scaled {
    width: 16rem;
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
.hypnotic-antagonist {
    background: repeating-linear-gradient(
      -45deg,
      #ff7477,
      #ff7477 7px,
      #ffffff 7px,
      #ffffff 20px
    );
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
      #ffffff 1.0rem
    );
}
.depolarizing-neuromuscular-blocker {
    background-color: #ff7477;
    background: linear-gradient(
        #000000 50%,
        #ff7477 50%
    );
    padding-top: 0.1rem;
}
.depolarizing-neuromuscular-blocker .top{
    color: #ff7477;
    padding-top: 0rem;
}
.depolarizing-neuromuscular-blocker .bottom {
    padding-top: 0.3rem;
}
.antiemetic {
    background-color: #EFBE7D;
}
.opioid {
    background-color: #71C5E8;
}

.opioid-antagonist {
    background: repeating-linear-gradient(
        -45deg,
        #71C5E8,
        #71C5E8 0.5rem,
        #ffffff 0.5rem,
        #ffffff 1.0rem
    );
}
.others {
    background-color: #ffffff;
}
.bordered {
    border: 1px solid #000000;
}
</style>
