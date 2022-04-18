<template>
    <div class="container-header">
        <div class="container">
            <div class="content-container-header row">
                <div class="container content-text col-sm-12 col-md-4 d-flex justify-content-center">
                    <h1 class="mb-2">{{titulo}}</h1>
                    <p class="mb-2 mt-2">{{texto}}</p>
                    <button class="mt-5" @click="redirect()">{{btnValue}}</button>
                </div>
                <div class="content-img col-sm-12 col-md-6 d-flex justify-content-start align-items-center">
                    <img class="img-fluid portal-img" :src="srcImg">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header',

    props: {
        srcImg: String,
        titulo: String,
        texto: String,
        imgBg: String,
        btnValue: String,
        btnRedirect: String
    },
    methods:{
        redirect() {
            const url = this.btnRedirect
            window.location.assign(`${url}`)
        }
    }
}
</script>

<style lang="scss" scoped>
.content-container-header{
    height: 80vh;
    .content-text{
    flex-direction: column;

    h1,
    p{
        color: white;
        
    }
    h1{
        font-weight: 500;
        font-size: 44px;
        line-height: 1.3em;
        text-shadow: #212529 0 0 5px;
    }
    
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
}

.container-header{
    background-position: center bottom 0;
    background-image: url(https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/img02.jpg),linear-gradient(180deg,#2e3857 0%,#212529 100%)!important;
    background-size: cover;
    height: 80vh;
}

.content-img{
    .portal-img{
        max-width:100%;
        transition: .5s ease-in-out;
        animation: imgPortalAnimated 1s;
    }

    @keyframes imgPortalAnimated {
        from{
            opacity: 0;
            transform: translate3d(50px, 0px, 0px);
        }
        to{
            transform: translate3d(0px, 0px, 0px);
        }
        
    }
}

@media screen and (max-width: 425px){
    .content-container-header{
        .content-text{
            display: flex;
            align-items: center;
            h1,
            p{
                padding: 10% 5% 0 5%;
                text-align: center;
            }
            h1{
                margin-top:10%;
            }
            p{
                width: 300px;
            }
            button{
                width: 40vw !important;
                margin-bottom: 10%;
            }
        }
    }

    .container-header{
        background-position: center bottom center;
        background-image: url(https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/img02.jpg),linear-gradient(180deg,#2e3857 0%,#212529 100%)!important;
        background-size: cover;
        height: 40vh;
        top: 10%;
    }
}

@media screen and (max-width: 1024px) {
    .content-container-header{
        .content-text{
            button{
                width: 20vw;
            }
        }
    }
}
</style>

