<template>
  
    <Header
      titulo="Elegant Payment Processing"
      texto="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco."
      srcImg="https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/finance-illustration-04.png"
      imgBg="https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/img02.jpg"
      btnValue="Learn More"
      btnRedirect="https://www.google.com"
    />
    <div class="container">
      <Finances
        littleTitle="Our Service"
        mainTitle="The new standard in digital payments"
        mainParagraph="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco. Lorem ipsum dolor sit amet, consectetur adipiscing elit."
      />
      <SendingPayment
        littleTitle="Sending Payments"
        mainTitle="Sending money home?"
        mainParagraph="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud"
        valueBtn="Learn More"
        redirectBtn="https://www.google.com"
        imgSendPay="https://www.elegantthemes.com/preview/Divi/wp-content/uploads/2018/01/finance-illustration-04.png"
      />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Finances from "./components/Finances.vue";
import SendingPayment from "./components/sendingPayment.vue";

export default {
  name: 'App',
  components: {
    Header,
    Finances,
    SendingPayment
}
}
</script>

<style lang="scss">
*{
  color: white;
  font-family: ubuntu;
}

body{
  background-color: #212529;
}
</style>
