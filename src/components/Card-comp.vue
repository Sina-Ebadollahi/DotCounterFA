<template>
  <div class="col-sm-6 justify-content-center align-items-center">
    <div
      class="container-fluid row border border-2 bg-warning"
      style="border-radius: 15px"
    >
      <div class="container my-3">
        <h1 :class="'display-3 text-center ' + textColor">{{ headerData }}</h1>
      </div>
      <h1
        :class="'display-6 text-center fw-bold ' + textColor"
        v-if="dotsCount != 0 && lang == 'En'"
      >
        {{ dotInfo }}{{ dotsCount }}
      </h1>
      <h1
        :class="'display-6 text-center fw-bold ' + textColor"
        v-if="dotsCount != 0 && lang != 'En'"
      >
        {{ dotsCount }}{{ dotInfo }}
      </h1>
      <div
        class="container border border-dark row fw-bold h3 my-2 py-2 align-items-center"
      >
        <h4
          v-if="lang == 'En'"
          :class="'h4 fw-italic col-md-4 text-start ' + textColor"
        >
          {{ inputLabel }}
        </h4>
        <input
          class="border-0 col-sm-8 text-end py-2 align-items-center"
          @input="changeInpVal"
          type="text"
          name=""
          id=""
        />
        <h4
          v-if="lang != 'En'"
          :class="'h4 fw-italic col-md-4 text-end ' + textColor"
        >
          {{ inputLabel }}
        </h4>
      </div>
    </div>
  </div>
</template>

<script>
const chars = {
  ب: 1,
  پ: 3,
  ت: 2,
  ث: 3,
  ج: 1,
  چ: 3,
  خ: 1,
  ذ: 1,
  ز: 1,
  ژ: 3,
  ژ: 3,
  ژ: 3,
  ژ: 3,
  ش: 3,
  ض: 1,
  ظ: 1,
  غ: 1,
  ف: 1,
  ق: 2,
  ن: 1,
};
export default {
  name: "Card-comp",
  data() {
    return {
      inpVal: "",
      dotsCount: 0,
      headerData: "شمارنده نقاط در متن",
      inputLabel: " : متن را وارد نمایید",
      textColor: "text-dark",
      dotInfo: " : تعداد نقاط در متن",
    };
  },

  updated() {
    this.lang == "En"
      ? (this.headerData = "Persian Dot Counter")
      : (this.headerData = "شمارنده نقاط در متن");
    this.lang == "En"
      ? (this.dotInfo = "Dot Count : ")
      : (this.dotInfo = " : تعداد نقاط در متن");
    this.lang == "En"
      ? (this.inputLabel = "Enter Text : ")
      : (this.inputLabel = " : متن را وارد نمایید");
    this.appTheme == "Light"
      ? (this.textColor = "text-dark")
      : (this.textColor = "text-dark");
  },
  methods: {
    changeInpVal(e) {
      this.dotsCount = 0;
      this.inpVal = e.target.value;
      this.checkDotsInSentence(this.inpVal);
    },
    checkDotsInSentence(a) {
      for (let i = 0; i < a.length; i++) {
        let tempChar = a.charAt(i);
        for (const w of Object.keys(chars)) {
          if (tempChar == w) {
            this.dotsCount += Number.parseInt(chars[w]);
            break;
          }
          if (tempChar == "ی" && a.charAt(i + 1) != "") {
            this.dotsCount += 2;
            break;
          }
        }
      }
    },
  },

  props: {
    appTheme: String,
    lang: String,
  },
};
</script>
<style scoped></style>
