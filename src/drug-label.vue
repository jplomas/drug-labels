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
    "><span>{{ concentration }} {{ units }}</span></p>
  </div>
</template>

<style scoped>
.drug-label {
    box-sizing: border-box;  
    width: 100%;
    padding: 0.4vh;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.2vh;
    text-align: center;
    border-radius: 1vh;
}
.drug-label .top {
    padding-top: 0.1vh;
    margin-top: 0.4vh;
    margin-bottom: 0.6vh;
    padding-bottom: 0.1vh;
}
.drug-label .bottom {
  margin-bottom: 0.1vh;
  padding-bottom: 0.6vh;
  margin-top: 0.1vh;
  padding-bottom: 0.1vh;
}
.scaled {
    width: 16vh;
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
      #FF8200,
      #FF8200 0.5vh,
      #ffffff 0.5vh,
      #ffffff 1.0vh
    );
}
.hypnotic-antagonist .top strong,
.hypnotic-antagonist .bottom span {
  background: #FFFFFF;
  padding: 0.2vh;
}
.neuromuscular-blocker {
    background-color: #ff7477;
}
.neuromuscular-blocker-antagonist {
    background: repeating-linear-gradient(
      -45deg,
      #ff7477,
      #ff7477 0.5vh,
      #ffffff 0.5vh,
      #ffffff 1.0vh
    );
}
.neuromuscular-blocker-antagonist .top strong,
.neuromuscular-blocker-antagonist .bottom span {
  background: #FFFFFF;
  padding: 0.2vh;
}
.depolarizing-neuromuscular-blocker {
    background-color: #ff7477;
    background: linear-gradient(
        #000000 50%,
        #ff7477 50%
    );
    padding-top: 0.1vh;
}
.depolarizing-neuromuscular-blocker .top{
    color: #ff7477;
    padding-top: 0vh;
}
.depolarizing-neuromuscular-blocker .bottom {
    padding-top: 0.3vh;
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
        #71C5E8 0.5vh,
        #ffffff 0.5vh,
        #ffffff 1.0vh
    );
}
.opioid-antagonist .top strong,
.opioid-antagonist .bottom span {
  background: #FFFFFF;
  padding: 0.2vh;
}
.vasopressor {
   background-color: #D6BFDD;
}
.anticholinergic {
    background-color: #A4D65E;
}
.adrenaline {
    background-color: #000000;
        background: linear-gradient(
        #000000 50%,
        #D6BFDD 50%
    );
    padding-top: 0.1vh;
}
.adrenaline .top{
    color: #D6BFDD;
    padding-top: 0vh;
}
.adrenaline .bottom {
    background-color: #D6BFDD;
    padding-top: 0.3vh;
}
.others {
    background-color: #ffffff;
}
.bordered {
    border: 1px solid #000000;
}
</style>
