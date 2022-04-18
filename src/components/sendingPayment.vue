<template>
  <div class="container">
      <div class="row sendPay d-flex justify-content-center mt-5 pt-5 mb-5 pb-5">
          <div data-img="left" class="col-sm-12 mainImg col-md-5">
              <img :src="imgSendPay" alt="" class="img-fluid">
          </div>
          <div class="col-sm-12 col-md-5 d-flex justify-content-center  flex-column">
                <div class="littleTitle">
                    <p>{{littleTitle}}</p>
                </div>
                <div class="mainTitle mt-3">
                    <h1>{{mainTitle}}</h1>
                </div>
                <div class="mainParagraph mt-4">
                    <p>{{mainParagraph}}</p>
                </div>
                <div class="col-sm-12 mainButton mt-4">
                  <button @click="redirect">{{valueBtn}}</button>
                </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'sendingPayment',

    props:{
        littleTitle:String,
        mainTitle:String,
        mainParagraph:String,
        valueBtn:String,
        redirectBtn:String,
        imgSendPay:String
    },
    methods:{
        redirect(){
            window.location.assign(`${this.redirectBtn}`)
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
.sendPay{
    

    .mainImg{
        img{
            padding-right: 15%;
        }
    }

    .littleTitle{
        p{
            font-weight: 600;
            color: #4DAAF2;
        }
    }

    .mainParagraph{
        opacity: .4;
    }

    .mainButton{
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
    [data-img="left"]{
        transform: translate3d(-50px, 0, 0);
    }
    [data-img].animated{
        opacity: 1;
        transform: translate3d(0, 0, 0);
    }

    /*-----------------------------
            Responsividade
    -----------------------------*/
    @media screen and (max-width: 1024px) {
        .mainButton{
            button{
                width: 15vw;
            }
        }
    }

    @media screen and (max-width: 768px) {
        .mainButton{
            button{
                width: 20vw;
            }
        }
    }

    @media screen and (max-width: 425px){
        .mainImg{
                img{
                    margin-bottom: 20%;
                }
            }

            .mainButton{
                display: flex;
                justify-content: center;
                button{
                    width: 50vw;
                }
            }
    }
}
</style>