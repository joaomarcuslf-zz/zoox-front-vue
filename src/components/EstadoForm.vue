<template>
  <div class="modal" :class="{ 'is-active': showModal }">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title" v-if="estado.nome || estado.abreviacao"> {{ $t("message.update") }} </p>
        <p class="modal-card-title" v-else> {{ $t("message.add") }} </p>
      </header>

      <section class="modal-card-body">
        <div class="field">
          <label class="label">{{ $t("message.name") }}</label>
          <div class="control">
            <input class="input" type="text" v-model="nome">
          </div>
        </div>

        <div class="field">
          <label class="label">{{ $t("message.abbr") }}</label>
          <div class="control">
            <input class="input" type="text" v-model="abreviacao">
          </div>
        </div>

        <div class="control">
          <a href="#" class="button is-link is-fullwidth" @click="submitData()">{{ $t("buttons.send") }}</a>
        </div>
      </section>
      <br />
    </div>

    <button class="modal-close is-large" aria-label="close" @click="toogleModal()"></button>
  </div>
</template>

<script>
import Vue from 'vue';

export default {
  data() {
    return {
      nome: this.estado.nome || '',
      abreviacao: this.estado.abreviacao || '',
    };
  },
  name: 'EstadoForm',
  i18n: {
    messages: {
      pt: {
        message: {
          add: "Adicionar Estado",
          update: "Atualizar Estado"
        }
      }
    }
  },
  props: {
    showModal: Boolean,
    toogleModal: Function,
    onSubmit: Function,
    estado: {
      type: Object,
      default: function() {
        return {};
      },
    },
  },
  methods: {
    submitData: function() {
      const newEstado = Object.assign({}, this.estado, {
        nome: this.nome,
        abreviacao: this.abreviacao.toUpperCase(),
      });

      return this.onSubmit(newEstado);
    },
  },
};
</script>
