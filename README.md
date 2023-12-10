# Typescript Labs

## Lab 11: Assigning Dynamic Keys to an Object

file: `/src/11-record.problem.ts`

Consider this `createCache` function:

```ts
const createCache = () => {
  const cache = {};

  const add = (id: string, value: string) => {
    cache[id] = value;
  };

  const remove = (id: string) => {
    delete cache[id];
  };

  return {
    cache,
    add,
    remove,
  };
};
```

We've got an empty object that we're calling cache, and we're allowing users to specify add and remove on it.

Inside the tests we have some errors:

```ts
    expect(cache.cache["123"]).toEqual("Matt")
```

Hovering over the errors makes it look like cache has been typed as an empty object.

There are also errors in the `createCache` function:

```bsh
Expression of type 'string' can't be used to index type '{}'
```

There is no indexing happening with our current code..

Challenge
Your challenge is to reference the TypeScript docs and work out what could be causing this problem.

Update cache to be typed properly so the errors go away.