<template>
    <div class="col-6  align-items-center">
        <div class="container-fluid row border border-2">
            <div class="container">
                <h1 class="display-2 text-center">{{ headerData }}</h1>
            </div>
            <h1 class="display-6 text-center fw-bold " v-if="dotsCount != 0">{{ dotsCount }} : تعداد نقاط </h1>
        <div class="container border border-dark fw-bold h3">
            <input class=" w-100 border-0 text-end" @input="changeInpVal"  type="text" name="" id="" >
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
  ش:3,
  ض:1,
  ظ:1,
  غ:1,
  ف:1,
  ق:2,
  ن:1,
}
    export default{
        name: 'Card-comp',
        data(){
            return{
                inpVal : "",
                dotsCount: 0,
                headerData: "شمارنده نقاط هر جمله"
            }
        },
        updated(){
            this.lang == 'En' ? this.headerData = "counter of any sentence" : this.headerData = "شمارنده نقاط هر جمله";
        },
        methods:{
            changeInpVal(e){
                this.dotsCount = 0;
                this.inpVal = e.target.value;
                this.checkDotsInSentence(this.inpVal)
            },
            checkDotsInSentence(a){
                for(let i =0; i < a.length; i++){
                    let tempChar = a.charAt(i);
                    for(const w of Object.keys(chars)){
                        if(tempChar == w){
                            this.dotsCount += Number.parseInt(chars[w]);
                            break;
                        }
                        if(tempChar == "ی" && a.charAt(i + 1) != ""){
                            this.dotsCount += 2;
                            break;
                        }
                    }
                }
            },
            
            
        },
        
        props:{
            appTheme: String,
            lang:String
            
        }

    }
</script>
<style scoped>

</style>