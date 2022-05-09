<template>
  <select v-model="$i18n.locale" @change="handleChange($i18n.locale)">
    <option v-for="(locale, i) in locales" :key="`locale-${i}`" :value="locale">
      {{ locale }}
    </option>
  </select>
</template>

<script>
export default {
  name: "LocaleSwitcher",
  data() {
    return { locales: ["az", "en"] };
  },
  mounted() {
    if (localStorage.Lang != null) this.$i18n.locale = localStorage.Lang;
  },
  methods: {
    handleChange(lang) {
      localStorage.Lang = lang;
    },
  },
};
</script>
