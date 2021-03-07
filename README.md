# tools

The CountryFinder filters text for country names and country codes and translates the opposite.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for uploading the files to a web-server
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

## Using the CountryFinder

The CountryFinder Tool uses the the ISO 3166-1 Alpha 3 country codes ([npm package]([hallo](https://www.npmjs.com/package/i18n-iso-countries))).
### Country Name to Code

Enter any text that contains country names to the first text box. The application automatically searches for any country names included and displays them in the second text box. Country codes in the second field do not contain duplicates.

### County Code to Name

Enter any text that contains country codes to the second text box. The application automatically search for any country codes and displays them in the second field. Country names in the second field do not contain duplicates.

Tip: If the list of countries contains a lot of false positives, check for case sensitive spelling.



