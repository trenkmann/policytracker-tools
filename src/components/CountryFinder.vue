<template>
  <section class="countryfinder">
    <h3>Country Name to Code</h3>
    <el-input
      v-model="inputFromName"
      type="textarea"
      :rows="2"
      placeholder="Enter text here"
    />
    <el-input
      v-model="foundFromName"
      type="textarea"
      :rows="2"
    />
    <h3>Country Code to Name</h3>
    <el-checkbox
      v-model="caseSensitiveFromCode"
      style="margin-bottom:10px"
    >
      Case Sensitive
    </el-checkbox>
    <el-input
      v-model="inputFromCode"
      type="textarea"
      :rows="2"
      placeholder="Enter text here"
    />
    <el-input
      v-model="foundFromCode"
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
      inputFromName: 'greece Greece Austira austria',
      inputFromCode: 'Aut GRC',
      caseSensitiveFromCode: false,
    };
  },
  computed: {
    foundFromName() {
      const cNames = Object.values(countries.getNames('en')).flat();

      const input = this.inputFromName?.toLowerCase();

      const resultsNames = cNames.filter(
        (country) => input.includes(country.toLowerCase()),
      );

      const results = resultsNames.map((c) => countries.getAlpha3Code(c, 'en'));

      return [...results].join('; ');
    },
    foundFromCode() {
      const cCodes = Object.keys(countries.getAlpha3Codes('en')).flat();

      const input = this.caseSensitiveFromCode
        ? this.inputFromCode
        : this.inputFromCode?.toUpperCase();

      const resultsCodes = cCodes.filter(
        (country) => input.includes(country.toUpperCase()),
      );

      const results = resultsCodes.map((c) => countries.getName(c, 'en'));

      return [...results].join('; ');
    },
  },
};
</script>
<style lang="scss">
.countryfinder{
  flex: 1 0 300px;
  max-width: 500px;
}
</style>
