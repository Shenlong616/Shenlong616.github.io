---
title: "Angular: Algolia instantsearch"
date: 2019-08-25 13:07:30 -0700
description: "Algolia Instantsearch with Angular 8"
tags: ["angular", "algolia"]
categories: ["Angular"]
canonicalURL: "https://github.com/fireship-io/fireship.io/blob/master/hugo/content/snippets/algolia-instantsearch-angular.md"
ShowCanonicalLink: true
---

## Install Instantsearch

Algolia provides official [Angular support](https://community.algolia.com/angular-instantsearch/). Follow the installation steps to make the prebuilt components available in your app.

## Angular Instantsearch Component

```html
<ais-instantsearch
  [config]="{
    apiKey: 'YOUR-SEARCH-ONLY-KEY',
    appId: 'YOUR-APP-ID',
    indexName: 'customers',
    routing: true
  }"
>
  <ais-search-box></ais-search-box>
  <ais-hits>
    <ng-template let-hits="hits" let-results="results">
      <div *ngIf="hits.length === 0">
        No results found matching <strong>{{results.query}}</strong>.
      </div>

      <div *ngIf="results.query">
        <div *ngFor="let hit of hits" class="content">
          <img [src]="hit.avatar" />
          <section>
            <h3>{{hit.username}} {{hit.objectID}}</h3>
            <ais-highlight attribute="bio" [hit]="hit"></ais-highlight>
          </section>
        </div>
      </div>
    </ng-template>
  </ais-hits>
</ais-instantsearch>
```
