---
title: "React: Algolia instantsearch"
author: "Jeff Delaney"
date: 2019-08-25 13:07:30 -0700
description: "Algolia InstantSearch with React"
tags: ["react", "algolia", "jsx"]
categories: ["React"]
canonicalURL: "https://github.com/fireship-io/fireship.io/blob/master/hugo/content/snippets/algolia-instantsearch-react.md"
ShowCanonicalLink: true
---

## Install InstantSearch

Algolia provides official [React support](https://www.algolia.com/doc/guides/building-search-ui/installation/react/). Follow the installation steps to make the prebuilt components available in your app.

## React InstantSearch Component

```jsx
import React from "react";
import "./App.css";

import algoliasearch from "algoliasearch/lite";
import {
  InstantSearch,
  SearchBox,
  Hits,
  connectHighlight,
} from "react-instantsearch-dom";

const searchClient = algoliasearch("YOUR-APP-ID", "YOUR-SEARCH-KEY");

function App() {
  return (
    <InstantSearch searchClient={searchClient} indexName="customers">
      <SearchBox />
      <Hits hitComponent={Hit} />
    </InstantSearch>
  );
}

const CustomHighlight = connectHighlight(({ highlight, attribute, hit }) => {
  const parsedHit = highlight({
    highlightProperty: "_highlightResult",
    attribute,
    hit,
  });

  return (
    <div>
      <h3>{hit.username}</h3>
      <img src={hit.avatar} alt={hit.username} />
      {parsedHit.map((part) =>
        part.isHighlighted ? <mark>{part.value}</mark> : part.value
      )}
    </div>
  );
});

const Hit = ({ hit }) => (
  <p>
    <CustomHighlight attribute="bio" hit={hit} />
  </p>
);

export default App;
```
