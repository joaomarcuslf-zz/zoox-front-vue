<template>
  <div class="select locale-changer">
    <select v-model="$i18n.locale">
      <option v-for="(lang, i) in langs" :key="`Lang${i}`" :value="lang.code">{{ lang.label }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'locale-changer',
  data () {
    return {
      langs: [
        {
          code: 'pt',
          label: 'Português'
        }, {
          code: 'en',
          label: 'English'
        }, {
          code: 'fr',
          label: 'Français'
        }
      ]
    }
  }
}
</script>
