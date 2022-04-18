<template>
    <div class="container mt-5 pt-5 pb-5">

        <div data-finance="left" class="mb-4 services col-md-5">
            <div class="mb-4 littleTitle">
                <p>{{littleTitle}}</p>
            </div>
            <div class="mb-4 mainTit">
                <h1>{{mainTitle}}</h1>
            </div>
            <div class="mb-5 mainParagraph">
                <p>{{mainParagraph}}</p>
            </div>
        </div>

        <div class="container-content row d-flex justify-content-center">
            <div 
                v-for="financeItem in financeItems" 
                :key="financeItem.id" 
                data-finance="down" 
                class="content-finance col-md-3 pb-4 pt-2"
            >
                <div class=" mt-4 d-flex justify-content-center align-items-center flex-column pb-3">
                    <img :src="financeItem.icone" alt="">
                </div>
                <div class="title-finance d-flex justify-content-center align-items-center flex-column">
                    <p>
                        {{financeItem.title}}
                    </p>
                </div>
                <div class="paragraph-finance d-flex justify-content-center align-items-center flex-column">
                    <p>{{financeItem.text}}</p>
                </div>
                <div class="link-finance d-flex justify-content-center align-items-center flex-column">
                    <a :href="financeItem.link" :class="financeItem.class">Read More<span :class="financeItem.class"> > </span></a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
    name: 'Finances',

    props: {
        littleTitle:String,
        mainTitle:String,
        mainParagraph:String
    },

    data: () => {
        return {
            financeItems: [
                {icone:'https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/finiance-icon-03.png',title: 'Send Money Instantly', text: 'Etiam magna arcu, ullamcorper ut pulvinar et, ornare sit amet ligula. Aliquam vitae bibendum lorem.', link:'link1', class: 'text-blue'},
                {icone:'https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/finiance-icon-02.png',title: 'Send Money Instantly', text: 'Etiam magna arcu, ullamcorper ut pulvinar et, ornare sit amet ligula. Aliquam vitae bibendum lorem.', link:'link2', class: 'text-green'},
                {icone:'https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/finiance-icon-01.png',title: 'Send Money Instantly', text: 'Etiam magna arcu, ullamcorper ut pulvinar et, ornare sit amet ligula. Aliquam vitae bibendum lorem.', link:'link3', class: 'text-red'}
            ]
        }
    },

    mounted(){
        const finance = document.querySelectorAll('[data-finance]');
        const animationClass = 'animate';

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
    .services{
        margin: 0 0 0 9%;

        .littleTitle{
            p{
                color: #4DAAF2;
                font-weight: 600;
            }
        }

        .mainParagraph{
            p{
                opacity: .6;
            }
        }
    }

    .content-finance{
        background-color: #2E3858;
        margin: 0 20px;
        transition: .3s ease-in-out all;
        border-radius: .5rem;

        &:hover{
            transform: scale(1.1) !important;
            box-shadow: 0 0 30px -1px #2E3858;
            border-radius: 1.5rem;

            
        }
        

        .title-finance{
            span{
                text-align: center;
                margin: 10px 0;
                font-weight: 600;

                
            }
        }
        .paragraph-finance{
            p{
                text-align: center;
            }
        }
        .link-finance{
            a{
                text-decoration: none;
                font-weight: 600;
                font-size: larger;
                transition: .5s;
                padding: .5rem .5rem;

                &:hover{
                    background-color: #2C3554;
                }
            }

            .text-blue  {color: #3699E6;}
            .text-green {color: #24C4A3;}
            .text-red   {color: #DF4570;}
        }

        
    }

    [data-finance]{
        opacity: 0;
        transition: 1s;
    }

    [data-finance="down"]{
        transform: translate3d(0, 50px, 0);
    }

    [data-finance="left"]{
        transform: translate3d(-50px, 0, 0);
    }

    [data-finance].animate{
        opacity: 1;
        transform: translate3d(0, 0, 0);
    }


    /*----------------------------------
    Responsividade
    ----------------------------------*/
    @media screen and (max-width: 768px) {
        .content-finance{
            .title-finance{
                text-align: center;
            }
            .paragraph-finance{
                p{
                    text-align: center;
                }
            }
        }
    }

    @media screen and (max-width: 425px) {
        .services{
            margin-top: 70vh;

            .mainParagraph{
                p{
                    width: 300px;
                }
            }
        }
        .content-finance{
            margin-top: 10%;
            width: 300px;

            &:hover{
                transform: scale(1) !important;
            }
        }
    }
</style>