<template>
  <div class="container">
    <div class="row d-flex justify-content-center">
      <div class="content col-md-4">
        
        <h1>teste</h1>

        <div v-for="resumeItem in resumeItems" :key="resumeItem.id" class="d-flex flex-column">
          <div class="mainImg">
            <img :src="resumeItem.img" class="img-fluid">
          </div>
          <div class="littleTitle">
            <p>{{resumeItem.littleTitle}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:'Resume',

    props:{
      resumeItems: [
        {imgA:String, littleTitleA:String, mainTitleA:String},
        {imgB:String, littleTitleB:String, mainTitleB:String},
        {imgC:String, littleTitleC:String, mainTitleC:String}
      ]
    },

    data: () => {
      // return{
      //   resumeItems: [
      //     {img:`${this.imgA}`, littleTitle:`${this.littleTitleA}`, mainTitle:'', mainParagraph:'', buttonValue:'', redirectBtn:`${this.redirectBtnA}`},
      //     {img:`${this.imgB}`, littleTitle:`${this.littleTitleB}`, mainTitle:'', mainParagraph:'', buttonValue:'', redirectBtn:`${this.redirectBtnB}`},
      //     {img:`${this.imgC}`, littleTitle:`${this.littleTitleC}`, mainTitle:'', mainParagraph:'', buttonValue:'', redirectBtn:`${this.redirectBtnC}`}
      //   ]
      // }
    }

    
}
</script>

<style>

</style>