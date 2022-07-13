---
title: "Svelte: Algolia instantsearch"
author: "Jeff Delaney"
date: 2019-08-25 13:07:30 -0700
description: "Algolia InstantSearch with Svelte 3"
tags: ["svelte", "algolia"]
categories: ["Svelte", "Algolia"]
canonicalURL: "https://github.com/fireship-io/fireship.io/blob/master/hugo/content/snippets/algolia-instantsearch-svelte.md"
ShowCanonicalLink: true
---

## Install Algolia

Algolia does not provide official support for [Svelte](https://svelte.dev), but we can easily implement our own custom UI with [AlgoliaSearch](https://github.com/algolia/algoliasearch-client-javascript).

Note. You can also use InstantSearch.js if you want pre-built components.

```shell
npm install algoliasearch
```

## Update the index.html

The Algolia client makes a reference to `process`, which does not exist in the browser. Add the code below to prevent errors.

```html
<title>Svelte app</title>

<!-- ADD THIS LINE -->
<script>
  window.process = { env: { DEBUG: undefined } };
</script>
```

## Svelte Algolia Search Component

The component below initializes the AlgoliaSearch _lite_, then binds a request to each _keyup_ event on a form input. Algolia returns an object with the resulting hits, which are updated on the component's `hit` property.

```html
<script>
  import { onMount } from "svelte";
  import algoliasearch from "algoliasearch/lite";

  let searchClient;
  let index;

  let query = "";
  let hits = [];

  onMount(() => {
    searchClient = algoliasearch("YOUR-APP-ID", "YOUR-SEARCH-ONLY-KEY");

    index = searchClient.initIndex("customers");

    // Warm up search
    index.search({ query }).then(console.log);
  });

  // Fires on each keyup in form
  async function search() {
    const result = await index.search({ query });
    hits = result.hits;
    console.log(hits);
  }
</script>

<style>
  :global(em) {
    color: red;
    font-weight: bold;
    background: black;
  }
</style>

<h1>Svelte InstantSearch</h1>

<div>
  <input type="text" bind:value="{query}" on:keyup="{search}" />
</div>

<img src="{hit.avatar}" alt="{hit.username}" />
<section>
  <h3>{hit.username} {hit.objectID}</h3>
  <!-- <p>{hit.bio}</p> -->

  <p contenteditable bind:innerHTML="{hit._highlightResult.bio.value}"></p>
</section>
```

![](/assets/images/0/svelte-algolia.png)
