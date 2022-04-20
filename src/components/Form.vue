<template>
    <img :src="imgWave" class="img-fluid">
  <div class="container-form">
      <div class="container">
          <div class="row">
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
              
                  <form class="mt-5 pt-5d-flex flex-column text-center col-md-5" action="">
                      <h2 class="mt-5 pt-5">{{formTitle}}</h2>
                      <div class="d-flex justify-content-center">
                          <p class="col-md-7">{{formText}}</p>
                      </div>
                      <div class="d-flex flex-column align-items-center">
                          <input class="mb-3" type="text" name="" id="" placeholder="Seu Nome">
                          <input class="mb-3" type="text" name="" id="" placeholder="Seu E-mail">
                          <input class="mb-3" type="number" name="" id="" placeholder="Seu Contato">
                      </div>
                  </form>
              
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
        formText:String

    }
}
</script>

<style lang="scss" scoped>
.container-form{
    background-image: linear-gradient(90deg,#6cdfee 0%,#538bf8 100%)!important;
}
form{
    background: white;
    margin-bottom: 10%;
    padding: 0 0 3rem 0;
    border-radius: 5%;
    transition: .5s ease-in-out all;
    box-shadow: 0 0 .5rem rgb(48, 48, 48);

    &:hover{
        border-radius: 10%;
            box-shadow: 0 0 2rem rgb(48, 48, 48);
    }
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

        &:focus{
            outline: none;
            box-shadow: 0 0 10px black;
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
</style>