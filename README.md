# Tribute
An `@mention` engine written in ES6.

### Initializing
There are two ways to initialize Tribute, by passing an array of "collections" or by passing one collection object.

```js
var tribute = new Tribute({
  values: [
    {key: 'Phil Heartman', value: 'pheartman'},
    {key: 'Gordon Ramsey', value: 'gramsey'}
  ]
})
```

#### A Collection
Collections are configuration objects for Tribute, you can have multiple for instance. This is useful for scenarios where you may want to match multiple trigger keys, such as `@` for users and `#` for projects.


Collection object shown with defaults:
```js
{
  // The symbol that starts the lookup
  trigger: '@',

  // The function that gets called on select that retuns the content to insert
  selectCallback: function (item) {
    return '@' + item.value;
  },

  // the column to search against in the object
  lookup: 'key',

  // the column that contains the content to insert by default
  fillAttr: 'value',

  // REQUIRED: the array of objects to match
  values: []
}
```

You can pass multiple collections on initialization by passing in an array of collection objects to `collection`.

```js
var tribute = new Tribute({
  collection: []
})
```