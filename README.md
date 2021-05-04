# Paymentshield Insurance Quote Results - VueJS App with Vuetify

Link to live site: https://crisbnp.github.io/quote-results/

## Brief:

- Take the design and turn it into a VueJS app using vuetify framework
- Develop it so it is responsive
- Make the toggles change the values on the Accidental damage from ‘+£XX.XX’ to ‘Included’
- None of the buttons have to do anything

### 📌 How I approached this:

- Broke the mockup design given into components: header, footer, main (progress + results components)
- Turned the design into a VueJS app (VUE 2 + Vuetify) and make it responsive across different viewports

### 📌 Design elements that I modified:

1. Progress bar: I believe this bar is a multi-step form where user has to complete each step of the form to be able to continue to the next one which eventually leads to genereation of results. So by adding tickboxes to completed form, this helps the users understand that they have completed the sections and are now on the last section with generated results.

2. Drop down menu says "Monthly" as the label. I have changed that to "Payment Plans" as I feel that will be better understood by users.

---

## To set up the app locally:

### Project setup

```
npm install
```

#### Compiles and hot-reloads for development

```
npm run serve
```

#### Compiles and minifies for production

```
npm run build
```

#### Lints and fixes files

```
npm run lint
```

#### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
