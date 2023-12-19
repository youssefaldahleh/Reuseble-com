<template>
  <form>
    <Textcom v-model="textValue" label="Text" type="text" placeholder="placeholder" hint-message="hint-message"
      error-message="error-message" required>{{ textValue }}
    </Textcom>

    <TextAreaCom v-model="TextAreaValue" label="Text Area" placeholder="placeholder" error-message="" required
      hint-message="hint-message">
      {{ title }}
    </TextAreaCom>

    <SelectCom :options="['optionssssss', 'test', 'test2']" hint-message="hint-message" error-message="error-messge"
      v-model="selectValue" required>
    </SelectCom>

    <checkBoxCom label="Yousef" v-model="checkBoxValue" value="yousef"></checkBoxCom>

    <checkBoxCom label="Mutasim" v-model="checkBoxValue" value="muatasem"></checkBoxCom>

    <checkBoxCom label="Tayseer" v-model="checkBoxValue" value="taysser"></checkBoxCom>
    {{ checkBoxValue }}
    <!-- <checkBoxCom label="checkBox 2" ></checkBoxCom> -->


    <RadioCom label="Ahmad" v-model="raidoValue" :value="['Ahmad', 'test']"> </RadioCom>
    <RadioCom label="mohamad" v-model="raidoValue" value="mohamad"> </RadioCom>
    <RadioCom label="test" v-model="raidoValue" value="test"> </RadioCom>


    <input class="submit" type="submit" @click="submit()" />
  </form>

  <buttonCom></buttonCom>
  <br>
  <buttonCom buttonText="elevated" variant="elevated" buttonSize="small" rounded="small"></buttonCom>
  <buttonCom buttonText="elevated" variant="elevated" buttonSize="regular" rounded="medium"></buttonCom>
  <buttonCom buttonText="elevated" variant="elevated" buttonSize="large" rounded="large"></buttonCom>
  <br>
  <buttonCom buttonText="flat" variant="flat" buttonSize="small" rounded="small"></buttonCom>
  <buttonCom buttonText="flat" variant="flat" buttonSize="regular" rounded="medium"></buttonCom>
  <buttonCom buttonText="flat" variant="flat" buttonSize="large" rounded="large"></buttonCom>
  <br>
  <buttonCom buttonText="outlined" variant="outlined" bkcolor="white" buttonSize="small" rounded="small"></buttonCom>
  <buttonCom buttonText="outlined" variant="outlined" bkcolor="white" buttonSize="regular" rounded="medium"></buttonCom>
  <buttonCom buttonText="outlined" variant="outlined" bkcolor="white" buttonSize="large" rounded="large"></buttonCom>
  <br>
  <buttonCom buttonText="text" variant="text" bkcolor="white"></buttonCom>
  <br>
  <buttonCom buttonText="flat" variant="flat" buttonSize="regular" rounded="medium" loading></buttonCom>
  <br>
  <buttonCom buttonText="block" variant="flat" buttonSize="large" rounded="large" block></buttonCom>
</template>

<script>
import checkBoxCom from "./components/checkBox-com.vue";
import SelectCom from "./components/Select-com.vue";
import TextAreaCom from "./components/TextArea-com.vue";
import Textcom from "./components/Text-com.vue";
import RadioCom from "./components/Radio-com.vue";
import buttonCom from "./components/button-com.vue";
export default {
  components: {
    Textcom,
    TextAreaCom,
    SelectCom,
    checkBoxCom,
    RadioCom,
    buttonCom
  },
  data() {
    return {
      textValue: "",
      TextAreaValue: "",
      selectValue: "",
      checkBoxValue: [],
      checkBox: true,
      raidoValue: []
    };
  },
  methods: {
    submit() {
      console.log(this.textValue);
      console.log(this.TextAreaValue);
      console.log(this.selectValue);
      console.log(this.checkBoxValue);
      console.log(this.raidoValue);
    },
  },
};
</script>

<style>
@import './assets/style.css';

#app {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.submit {
  display: block;
}

button {
  margin: 20px;
}
</style>
