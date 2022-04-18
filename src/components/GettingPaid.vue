<template>
  <div class="container">
      <div class="row container-content d-flex justify-content-center mt-5 mt-2 pt-5 mb-5 pb-5">
          <div class="col-sm-11 col-md-5 d-flex flex-column justify-content-center">
                <div class="littleTitle">
                    <p>{{littleTitle}}</p>
                </div>
                <div class="mainTitle mt-3">
                    <h1>{{mainTitle}}</h1>
                </div>
                <div class="mainParagraph mt-4">
                    <p>{{mainParagraph}}</p>
                </div>
                <div class="mainBtn mt-4">
                    <button @click="redirect">{{mainBtn}}</button>
                </div>
          </div>
          <div data-img="right" class="col-sm-1 col-md-5 d-flex flex-column justify-content-center">
              <img :src="imgGetPay" alt="" class="img-get-pay img-fluid">
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'GettingPaid',

    props:{
        littleTitle:String,
        mainTitle:String,
        mainParagraph:String,
        mainBtn:String,
        btnRedirect:String,
        imgGetPay:String
    },
    methods:{
        redirect(){
            window.location.assign(`${this.btnRedirect}`)
        }
    },
    mounted(){
        const finance = document.querySelectorAll('[data-img]');
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

.littleTitle{
        p{
            font-weight: 600;
            color: #4DAAF2;
        }
    }

.mainParagraph{
        opacity: .4;
    }

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

[data-img]{
    opacity: 0;
    transition: 1s;
}
[data-img="right"]{
    transform: translate3d(50px, 0, 0);
}
[data-img].animated{
    opacity: 1;
    transform: translate3d(0, 0, 0);
}

/*---------------------------------
        Responsividade
---------------------------------*/
@media screen and (max-width: 1024px){
    .mainBtn{
        button{
            width: 15vw;
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
    .container-content{
        display: flex;
        flex-direction: column-reverse;

        .mainBtn{
            display: flex;
            justify-content: center;
            button{
                width: 50vw
            }
        }
        .img-get-pay{
            margin-bottom: 10vh;
        }
    }
    [data-img="right"]{
        transform: translate3d(0, 50px, 0);
    }
}
</style>