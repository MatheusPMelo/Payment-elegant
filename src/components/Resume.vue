<template>
  <div class="container">
    <div class="mt-5 pt-5 mb-5 pb-5">
      <div class="content row mt-5">
        
        <!-- Content 1 --->
        <div data-animation="right" class="col-md-4 mb-5 container">
          <div class="d-flex flex-column">
            <div class="">
              <div class="imgContent1 d-flex justify-content-center">
                <img :src="imgA" class="img-fluid">
              </div>
              <div class="littleTitle pt-3">
                <p class="text-center">{{littleTitleA}}</p>
              </div>
              <div class="mainHeader">
                <h1 class="text-center">{{mainTitleA}}</h1>
              </div>
              <div class="mainParagraph">
                <p class="text-center">{{mainParagraphA}}</p>
              </div>
              <div class="d-flex justify-content-center mainBtn">
                <button>{{btnValue}}</button>
              </div>
            </div>
          </div>
        </div>
        <!-- End Content 1 -->

        <!-- Content 2 --->
        <div data-animation="up" class="col-md-4 mb-5 container">
          <div class="d-flex flex-column">
            <div class="">
              <div class="imgContent1 d-flex justify-content-center">
                <img :src="imgB" class="img-fluid">
              </div>
              <div class="littleTitle pt-3">
                <p class="text-center">{{littleTitleB}}</p>
              </div>
              <div class="mainHeader">
                <h1 class="text-center">{{mainTitleB}}</h1>
              </div>
              <div class="mainParagraph">
                <p class="text-center">{{mainParagraphB}}</p>
              </div>
              <div class="d-flex justify-content-center mainBtn">
                <button>{{btnValue}}</button>
              </div>
            </div>
          </div>
        </div>
        <!-- End Content 2 -->

        <!-- Content 3 --->
        <div data-animation="left" class="col-md-4 mb-5 container">
          <div class="d-flex flex-column">
            <div class="">
              <div class="imgContent1 d-flex justify-content-center">
                <img :src="imgC" class="img-fluid">
              </div>
              <div class="littleTitle pt-3">
                <p class="text-center">{{littleTitleC}}</p>
              </div>
              <div class="mainHeader">
                <h1 class="text-center">{{mainTitleC}}</h1>
              </div>
              <div class="mainParagraph">
                <p class="text-center">{{mainParagraphC}}</p>
              </div>
              <div class="d-flex justify-content-center mainBtn">
                <button>{{btnValue}}</button>
              </div>
            </div>
          </div>
        </div>
        <!-- End Content 3 -->
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:'Resume',

    props:{
          btnValue:String,

          imgA:String, 
          littleTitleA:String, 
          mainTitleA:String,
          mainParagraphA:String,
          btnRedirectA:String,
       
          imgB:String, 
          littleTitleB:String, 
          mainTitleB:String,
          mainParagraphB:String,
          btnRedirectB:String,

          imgC:String, 
          littleTitleC:String, 
          mainTitleC:String,
          mainParagraphC:String,
          btnRedirectC:String
    },
    mounted(){
        const finance = document.querySelectorAll('[data-animation]');
        const animationClass = 'animated';

        function animeScroll() {
          const windowTop = window.pageYOffset + ((window.innerHeight * 3) / 4);
          finance.forEach(function(element) {
            if((windowTop) > element.offsetTop) {
              element.classList.add(animationClass);
            } else {
              element.classList.remove(animationClass);
            }
            console.log(element)
          })
        }
        window.addEventListener('scroll', ()=>{
            animeScroll();
        })
    }   
}
</script>

<style lang="scss" scoped>

.mainBtn{
    button{
        width: 10vw;
        padding: .4rem 1.4rem;
        border: 5px solid #4DAAF2;
        border-radius: 2rem;
        box-shadow: #4DAAF2 0 0 20px;
        color: white;
        background-color: #4DAAF2;
        transition: .5s ease-in-out all;
        font-weight: 600;
        &:hover{
            background-color: white;
            color: #4DAAF2;
            animation: shadowAnimated 2s infinite ease-in-out;
        }
        @keyframes shadowAnimated {
            0%{
                box-shadow: #4DAAF2 0 0 20px;
            }
            50%{
                box-shadow: #4DAAF2 0 0 10px;
            }
            100%{
                box-shadow: #4DAAF2 0 0 20px;
            }
        }
    }
}

[data-animation]{
  opacity: 0;
  transition: 1s;
}

[data-animation="up"]{
  transform: translate3d(0, -100px, 0);
}
[data-animation="left"]{
  transform: translate3d(0 ,100px, 0);
}
[data-animation="right"]{
  transform: translate3d(0, 100px, 0);
}
[data-animation].animated{
  opacity: 1;
  transform: translate3d(0, 0, 0);
}


/*----------------------------
    Responsividade
----------------------------*/
@media screen and (max-width:1024px) {
  .mainBtn{
    button{
      width: 17vw;
    }
  }
}

@media screen and (max-width: 768px){
  .mainBtn{
    button{
      width: 20vw;
    }
  }
}

@media screen and (max-width: 425px){
  .mainBtn{
    button{
      width: 40vw;
    }
  }
}
</style>