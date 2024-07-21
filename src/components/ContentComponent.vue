<template>
  <div class="container">
    
    <main class="main-content">
    <section class="discount-section">
      <div class="discount-badge">50% DE DESCONTO</div>
      
    </section>
    <section class="email-section">
      <form @submit.prevent="redeemOffer">
        <label for="email">E-MAIL</label>
        <input 
          type="email" 
          id="email" 
          v-model="email" 
          placeholder="Digite seu e-mail" 
          :class="{ 'input-error': emailError }"
        >
        <span v-if="emailError" class="error-message">{{ emailError }}</span>
        <button type="submit">Resgatar Oferta</button>
      </form>
    </section>
    <section class="description-section">
      <h3>Projetada para Imersão</h3>
      <p>Alimentada pela Google</p>
    </section>
  </main>
    

  

  <div class="main-img">

        <img src="../assets/test.png" >
  </div>
 </div>
    

    
</template>

<script>
export default {
  name: 'ContentComponent',
  data() {
    return {
      email: '',
      emailError: ''
    }
  },
  methods: {
    validateEmail(email) {
      const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@(([^<>()[\]\\.,;:\s@"]+\.)+[^<>()[\]\\.,;:\s@"]{2,})$/i;
      return re.test(String(email).toLowerCase());
    },
    redeemOffer() {
      if (this.validateEmail(this.email)) {
        alert(`Oferta resgatada para o e-mail: ${this.email}`);
        this.emailError = '';
      } else {
        this.emailError = 'Por favor, insira um e-mail válido.';
      }
    }
  }
}
</script>

<style scoped>
.main-content {
  
  display:flex;
  flex-direction:column;
  justify-content: space-between;

  
  
}
.main-img{
  display: flex;
  
  flex-direction: start;
  margin-right: 30px ;
  padding-right:300px;
  
}
 
.discount-section {
  margin: 20px 0;

  
}

.discount-badge {
  background-color: red;
  color: white;
  padding: 10px;
  font-size: 1.2em;
  border-radius: 5px;
}
  

.email-section {
 margin-top: 30px;
  
 
}

.email-section label {
  display: block;
  margin-bottom: 10px;
  font-size: 1.2em;
 
}

.email-section input {
  padding: 10px;
  font-size: 1em;
  width: 100%;
  max-width: 300px;
  margin: 0 auto;
  display: block;
  margin-bottom: 10px;
}

.email-section button {
  padding: 10px 20px;
  font-size: 1em;
  background-color: blue;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.email-section button:hover {
  background-color: rgb(193, 221, 70);
}

.input-error {
  border: 1px solid rgb(182, 14, 112);
}

.error-message {
  color: rgb(218, 217, 217);
  font-size: 0.9em;
}

.description-section {
  margin: 20px 0;
}

.description-section h3 {
  font-size: 1.5em;
  margin: 10px 0;
}

.description-section p {
  font-size: 1.2em;
  color: #e1dfe6;
}
.container{
  display: flex;
  justify-content:space-around;
}
</style>
