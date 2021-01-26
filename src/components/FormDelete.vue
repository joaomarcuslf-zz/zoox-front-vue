<template>
  <div class="modal" :class="{ 'is-active': showModal }">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title"> {{ $t("message.confirmationTitle") }} </p>
      </header>

      <section class="modal-card-body">
        <h2>{{ $t("message.removalConfirmation") }}</h2>

        <br />
        <div class="control">
          <a href="#" class="button is-fullwidth is-danger" @click="onSubmit()">{{ $t("buttons.send") }}</a>
        </div>
      </section>
      <br />
    </div>

    <button class="modal-close is-large" aria-label="close" @click="toogleModal()"></button>
  </div>
</template>

<script>
export default {
  name: 'FormDelete',
  props: {
    showModal: Boolean,
    toogleModal: Function,
    onSubmit: Function,
  },
};
</script>
