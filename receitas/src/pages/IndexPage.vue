IndexPage.vue:
<template>
  <q-page class="q-pa-md">
    <div class="q-gutter-md">
      <div class="ingredientes q-card">
        <div class="q-card__section incluir-section">
          <div class="text-h6">Ingredientes:</div>
          <ul>
            <li v-for="ing in ingredientes" :key="ing.nome">{{ ing.nome }}</li>
          </ul>
          <q-input
            v-model="ingredienteInput"
            label="Incluir ingrediente"
            dense
            outlined
          />
          <q-btn @click="incluirIngrediente" label="Incluir" class="q-mt-md" />
        </div>
      </div>

      <div class="receitas q-card">
        <div class="q-card__section">
          <div class="text-h6">Receitas:</div>
          <div v-for="rec in receitas" :key="rec.id">
            <card-receita :receita="rec" />
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import servicos from "src/services/servicos";

import CardReceita from "../components/CardReceita.vue";

export default defineComponent({
  components: { CardReceita },
  name: "IndexPage",
  data() {
    return {
      ingredienteInput: "",
      ingredientes: [],
      receitas: [],
    };
  },
  created() {
    servicos.getAllIngredientes((dados) => {
      this.ingredientes = dados;
    });
    servicos.getAllReceitas((dados) => {
      this.receitas = dados;
    });
  },
  methods: {
    incluirIngrediente() {
      servicos.postIngrediente({ nome: this.ingredienteInput }, (dado) => {
        this.ingredientes.push(dado);
      });
      this.ingredienteInput = "";
    },
  },
});
</script>

<style lang="scss">
@import "../css/app.scss";
</style>
