<template>
  <div class="container-sm col-12 col-md-8 col-xl-6 mb-3">
    <p>Mensagem</p>
    <form id="burguer-from">
      <div class="mb-3">
        <label for="clientName" class="form-label">Nome do Cliente</label>
        <input
          v-model="nameClient"
          type="text"
          name="clientName"
          class="form-control"
          id="clientName"
          placeholder="Digite seu nome!"
        />
      </div>

      <div class="mb-3">
        <label for="bread" class="form-label">Escolha o pão: </label>

        <select
          v-model="breadClient"
          id="bread"
          name="bread"
          class="form-select"
        >
          <option v-for="breadServer in breadsServer" :key="breadServer.id" :value="breadServer.tipo"> {{breadServer.tipo}} </option>
        </select>
      </div>

      <div class="mb-3">
        <label for="meat" class="form-label"
          >Escolha a carne do seu Burguer:
        </label>
        <select
          v-model="meatClient"
          id="meat"
          name="meat"
          class="form-select"
        
        >
          <option v-for="meatServer in meatsServer" :key="meatServer.id" :value="meatServer.tipo">{{meatServer.tipo}}</option>
        </select>
      </div>

      <div class="mb-3">
        <label for="optional" class="form-label"
          >Escolha a carne do seu Burguer:
        </label>

        <div class="row p-3">

          <div v-for="optionalServer in optionalsServer" :key="optionalServer.id" class="form-check col-3">
            <input
              v-model="optionalsClient"
              :value="optionalServer.tipo"
              class="form-check-input"
              type="checkbox"
              :id="optionalServer.tipo"
              :name="optionalServer.tipo"
            />
            <label
              class="form-check-label border border-0"
              :for="optionalServer.tipo"
            >
              {{optionalServer.tipo}}
            </label>
          </div>

        </div>

      </div>
      <div class="text-end">
         <input id="submit-btn" type="submit" value="Criar meu burguer!" class="fw-bold btn btn-dark text-warning py-2 px-5 rounded-0 border-2 border-dark">
      </div>
    </form>
  </div>
</template>

<script>

export default {
  name: "BurguerForm",
  data(){
    return {
        nameClient: null,
        breadClient: null,
        meatClient: null,
        optionalsClient: null,
        breadsServer: [],
        meatsServer: [],
        optionalsServer: [],
        status: 'Solicitado',
        msg: null
    }
  }, 
  methods: {
    async getIngredientsInServer(){
        const response = await fetch("http://localhost:3000/ingredientes");
        const data = await response.json();

        this.breadsServer = data.paes;
        this.meatsServer = data.carnes;
        this.optionalsServer = data.opcionais;

        console.log(data)
    }
  },
  mounted(){
    this.getIngredientsInServer();
  }
};

</script>

<style scoped>

#submit-btn:hover{
    background: white !important;
    color: black !important;
    border-color: black !important;
}

label {
  border-left: 5px solid #ffc107;
  padding-left: 5px;
  font-weight: bold;
}
</style>