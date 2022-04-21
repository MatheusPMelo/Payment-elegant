<template>
    <img :src="imgWave" class="img-fluid">
  <div class="container-form">
      <div class="container mobile">
          <div class="row mobile">
              <div class="content-resume-form col-md-5 mt-5 pt-5 mb-5 pb-5">
                    <h1 class="mainTitle mt-5">
                      {{titleMain}}
                    </h1>
                    <p class="mainText mb-3">
                      {{mainText}}
                    </p>
                    <div class="listResume">
                        <ul>
                            <li>
                                <strong>&rarr; </strong>{{listItemA}}
                            </li>
                            <li>
                                <strong>&rarr; </strong>{{listItemB}}
                            </li>
                            <li>
                                <strong>&rarr; </strong>{{listItemC}}
                            </li>
                        </ul>
                    </div>
              </div>
              
                  <div class="form">
                    <form class="mt-5 pt-5d-flex flex-column text-center col-md-5" action="">
                        <h2 class="mt-5 pt-5">{{formTitle}}</h2>
                        <div class="d-flex justify-content-center">
                            <p class="col-md-7">{{formText}}</p>
                        </div>
                        <div class="d-flex flex-column align-items-center">
                            <input class="mb-3" type="text" name="" id="" placeholder="Seu Nome">
                            <input class="mb-3" type="text" name="" id="" placeholder="Seu E-mail">
                            <input class="mb-3" type="text" name="telefone" id="telefone" maxlength="15" placeholder="Seu telefone">
                            <input type="submit" :value="btnSubmit">
                        </div>
                    </form>
                  </div>
              
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name:'Form',

    props:{
        imgWave:String,

        titleMain:String,
        mainText:String,

        listItemA:String,
        listItemB:String,
        listItemC:String,

        formTitle:String,
        formText:String,
        btnSubmit:String

    },
    mounted(){
            function mascara(o,f){
        v_obj=o
        v_fun=f
        setTimeout("execmascara()",1)
        }
        function execmascara(){
            v_obj.value=v_fun(v_obj.value)
        }
        function mtel(v){
            v=v.replace(/D/g,"");             
            v=v.replace(/^(d{2})(d)/g,"($1) $2");
            v=v.replace(/(d)(d{4})$/,"$1-$2");   
            return v;
        }
        function id( el ){
            return document.getElementById( el );
        }
        window.onload = function(){
            id('telefone').onkeypress = function(){
                mascara( this, mtel );
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.container-form{
    background-image: linear-gradient(90deg,#6cdfee 0%,#538bf8 100%)!important;
}
.form{
    max-width: 40vw;
    form{
        background: white;
        width: 100%;
        margin-bottom: 10%;
        padding: 0 0 3rem 0;
        border-radius: 5%;
        transition: .5s ease-in-out all;
        box-shadow: 0 0 .5rem rgb(48, 48, 48);
        h2{
            color: #4DABF4;
            font-weight: 300;
        }
        p{
            color: rgba(0, 0, 0, 0.637);
            margin: 5% 0 5% 0;
        }
        input{
            width: 70%;
            border: solid #538bf8 3px;
            border-radius: 1rem;
            padding: .5rem;
            transition: .2s ease-in-out all;
            color: rgb(65, 65, 65);

            &:focus{
                outline: none;
                box-shadow: 0 5px 5px  #538af89d;
                transform: scale(1.1);
            }
        }
    }
}

.content-resume-form{
    margin: 0 7% 5%;
    h1{
        margin-bottom: 5%;
    }
    .listResume{
        ul{
            li{
                list-style: none;
                strong{
                    font-size: 30px;
                }
            }
        }
    }
}

/*--------------------------------
        Responsividade
--------------------------------*/
@media screen and (width: 2560px) {
    .container-form{
        .mobile{
            .content-resume-form{
                margin: 0;
            }
            .form{
                margin-top: 5%;
                width: 30vw;
            }
        }
    }
}
@media screen and (max-width: 1440px) {
    .mobile{
        div{
            .form{
                margin-top: 8%;
            }
        }
    }
}
@media screen and (max-width: 1024px) {
    .mobile{
        div{
            .form{
                margin-top: 12%;
            }
        }
    }
}
@media screen and (max-width: 768px) {
    .mobile{
        div{
            .form{
                margin-top: 15%;
            }
        }
    }
}
@media screen and (max-width: 425px) {
    .mobile{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        align-content: center;

        div{
            .form{
                max-width: 100%;
                form{
                    width: 100%;
                    p{
                        margin: 5%;
                    }
                }
            }
        }
    }
}
</style>