### Basic Usage

```js
let value = '7321234567'
let masked = false

<example label="US Phone Number">
  <input-facade mask="(###) ### - ####" v-model="value" :masked="masked" />
</example>

<checkbox v-model="masked" />
<display :value="value" />
```

### Dynamic Masks

Accepts an array of masking pattern and dynamically chooses the appropriate one based on the number of characters in the field.

```js
let value = ''
let masked = true

<example label="US Zip Code">
  <input-facade v-model="value" :mask="['#####', '#####-####']" :masked="masked" />
</example>

<checkbox v-model="masked" />
<display :value="value" />
```

### Custom Tokens

You can override the tokens on a per field basis. Just pass in your own token definition to the field.

```js
let value = ''
let masked = false

let hexTokens = {
  F: {
    pattern: /[0-9A-F]/i,
    transform: v => v.toLocaleUpperCase()
  }
}

<example label="Hex Color">
  <input-facade mask="\#FFFFFF" :tokens="hexTokens" :masked="masked" v-model="value" />
</example>

<checkbox v-model="masked" />
<display :value="value" />
```
