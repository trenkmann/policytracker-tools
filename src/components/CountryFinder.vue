<template>
  <section class="countryfinder">
    <el-input
      v-model="input"
      type="textarea"
      :rows="2"
      placeholder="Enter text here"
    />
    <el-input
      v-model="found"
      type="textarea"
      :rows="2"
    />
  </section>
</template>

<script>
import countries from 'i18n-iso-countries';
import english from 'i18n-iso-countries/langs/en.json';

countries.registerLocale(english);

export default {
  name: 'CountryFinder',
  data() {
    return {
      input: 'greece Greece Austira austria',
    };
  },
  computed: {
    lowercaseInput() {
      return this.input?.toLowerCase();
    },
    found() {
      const cNames = Object.values(countries.getNames('en')).flat();

      const resultsNames = cNames.filter(
        (country) => this.lowercaseInput.includes(country.toLowerCase()),
      );

      const results = resultsNames.map((c) => countries.getAlpha2Code(c, 'en'));

      return [...results].join('; ');
    },
  },
};
</script>
