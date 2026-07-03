# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: ui/products/search.spec.ts >> Product search >> search for "zzz-nonexistent-product-xyz" returns no products @regression
- Location: tests/ui/products/search.spec.ts:21:5

# Error details

```
TimeoutError: locator.fill: Timeout 10000ms exceeded.
Call log:
  - waiting for locator('#search_product')
    - waiting for navigation to finish...
    - navigated to "https://automationexercise.com/products"

```

# Page snapshot

```yaml
- generic [ref=e4]: Please wait while your request is being verified...
```

# Test source

```ts
  1  | import type { Page } from '@playwright/test';
  2  | import { BasePage } from './base.page';
  3  | import { ProductCardComponent } from '../components/productCard.component';
  4  | 
  5  | export class ProductsPage extends BasePage {
  6  |   constructor(page: Page) {
  7  |     super(page);
  8  |   }
  9  | 
  10 |   get searchInput() {
  11 |     return this.page.locator('#search_product');
  12 |   }
  13 | 
  14 |   get searchButton() {
  15 |     return this.page.locator('#submit_search');
  16 |   }
  17 | 
  18 |   get searchedProductsTitle() {
  19 |     return this.page.locator('h2.title', { hasText: 'Searched Products' });
  20 |   }
  21 | 
  22 |   get allProductsTitle() {
  23 |     return this.page.locator('h2.title', { hasText: 'All Products' });
  24 |   }
  25 | 
  26 |   get productCards() {
  27 |     return this.page.locator('.product-image-wrapper');
  28 |   }
  29 | 
  30 |   async open(): Promise<void> {
  31 |     await this.goto('/products');
  32 |   }
  33 | 
  34 |   async search(term: string): Promise<void> {
> 35 |     await this.searchInput.fill(term);
     |                            ^ TimeoutError: locator.fill: Timeout 10000ms exceeded.
  36 |     await this.searchButton.click();
  37 |   }
  38 | 
  39 |   card(index: number): ProductCardComponent {
  40 |     return ProductCardComponent.byIndex(this.page, index);
  41 |   }
  42 | 
  43 |   cardByProductId(productId: number): ProductCardComponent {
  44 |     return ProductCardComponent.byProductId(this.page, productId);
  45 |   }
  46 | 
  47 |   async resultCount(): Promise<number> {
  48 |     return this.productCards.count();
  49 |   }
  50 | }
  51 | 
```