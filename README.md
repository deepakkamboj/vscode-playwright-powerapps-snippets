# Playwright Code Snippets

![Build status](https://github.com/deepakkamboj/vscode-playwright-powerapps-snippets/workflows/main/badge.svg?branch=main)
[![Extension version](https://img.shields.io/vscode-marketplace/v/deepakkamboj.vscode-playwright-powerapps-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deepakkamboj.vscode-playwright-powerapps-snippets)
[![Extension installs](https://img.shields.io/vscode-marketplace/i/deepakkamboj.vscode-playwright-powerapps-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deepakkamboj.vscode-playwright-powerapps-snippets)
[![Semantic release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

## Getting Started
This Visual Studio Code extension adds predefined useful code snippets for 🎭 [Playwright](https://github.com/microsoft/playwright).

### Used tools for Playwright Integration Tests

- [playwright](https://playwright.dev/) - Playwright is a Node.js library to automate tests cases for Chromium, Firefox and WebKit with a single API
- [@playwright/test](https://playwright.dev/docs/api/class-test) - Playwright Test provides a test function to declare tests and expect function to write assertions.
- [playwright-core](https://www.npmjs.com/package/playwright-core) - This package contains the no-browser flavor of Playwright.

## 👨🏻‍🏫 How to Use

The first thing you need to do is installing the [VsCode Extension](https://marketplace.visualstudio.com/items?itemName=deepakkamboj.vscode-playwright-powerapps-snippets).

Basically, there are two ways to apply the snippets:

### 1. Direct Typing

Start typing the prefix (e.g. `pw-`) or just part of the snippet. Then, locate the snippets on the suggestions list and click on `TAB` or `ENTER`.

### 2. Command Palette

Open the Command Palette and type `Insert Snippet`. Then, simply choose the dedicated snippet.

## Code Snippets

The following snippets are provided by this package. If you have ideas of other snippets that would be helpful, please [open an issue](https://github.com/deepakkamboj/vscode-playwright-powerapps-snippets/issues/new).

### Playwright Test Blocks

#### `pw-describe`

```ts
test.describe('$1', () => {
  $0
});
```

#### `pw-test`

```ts
test('$1', async ({ page }) => {
  $0
});
```

#### `pw-beforeEach`

```ts
test.beforeEach(async ({ page }) => {
  $0
});
```

#### `pw-afterEach`

```ts
test.afterEach(async ({ page }) => {
  $0
});
```

#### `pw-beforeAll`

```ts
test.beforeAll(async ({ browser }) => {
  $0
});
```

#### `pw-afterAll`

```ts
test.afterAll(async ({ browser }) => {
  $0
});
```

#### `pw-step`

```ts
await test.step('$1', async () => {
  $0
});
```

#### `pw-use`

```ts
test.use({ $0 });
```

## Contributing

This is an open source project. Any contribution would be greatly appreciated!