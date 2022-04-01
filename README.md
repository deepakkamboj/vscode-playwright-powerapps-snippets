# Playwright Code Snippets

![Build status](https://github.com/deepakkamboj/vscode-playwright-test-snippets/workflows/main/badge.svg?branch=main)
[![Extension version](https://img.shields.io/vscode-marketplace/v/deepakkamboj0121.vscode-playwright-test-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deepakkamboj0121.vscode-playwright-test-snippets)
[![Extension installs](https://img.shields.io/vscode-marketplace/i/deepakkamboj0121.vscode-playwright-test-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=deepakkamboj0121.vscode-playwright-test-snippets)
[![License](https://img.shields.io/badge/license-MIT-lightgray.svg)](https://github.com/deepakkamboj/vscode-playwright-test-snippets/blob/main/LICENSE)

<!--[![Semantic release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)-->

## Getting Started
This Visual Studio Code extension adds predefined useful code snippets for 🎭 [Playwright](https://github.com/microsoft/playwright).

### Used tools for Playwright Integration Tests

- [playwright](https://playwright.dev/) - Playwright is a Node.js library to automate tests cases for Chromium, Firefox and WebKit with a single API
- [@playwright/test](https://playwright.dev/docs/api/class-test) - Playwright Test provides a test function to declare tests and expect function to write assertions.
- [playwright-core](https://www.npmjs.com/package/playwright-core) - This package contains the no-browser flavor of Playwright.

## 👨🏻‍🏫 How to Use

The first thing you need to do is installing the [VsCode Extension](https://marketplace.visualstudio.com/items?itemName=deepakkamboj0121.vscode-playwright-test-snippets).

Basically, there are two ways to apply the snippets:

### 1. Direct Typing

Start typing the prefix (e.g. `pw-`) or just part of the snippet. Then, locate the snippets on the suggestions list and click on `TAB` or `ENTER`.

### 2. Command Palette

Open the Command Palette and type `Insert Snippet`. Then, simply choose the dedicated snippet.

## Code Snippets

The following snippets are provided by this package. If you have ideas of other snippets that would be helpful, please [open an issue](https://github.com/deepakkamboj/vscode-playwright-test-snippets/issues/new).

### Anatomy of Playwright test

```ts
import { test } from '@playwright/test';

// Define the test suite to logically group tests
test.describe('$1', () => {
  //Repeating Setup for each Test
  test.beforeEach(async ({ page }) => {
    //..
  });

  test.afterEach(async ({ page }) => {
    //..
  });

  // One-Time Setup for test suite
  test.beforeAll(async ({ browser }) => {
    //..
  });

  test.afterAll(async ({ browser }) => {
    //..
  });

  test('$0', async ({ page }) => {});
});
```

Here are the details of the above test code snippet:

- Use `test.describe(title, callback)` to declare the test suite for the test cases.
```ts
test.describe('two tests', () => {
  test('one', async ({ page }) => {
    // ...
  });

  test('two', async ({ page }) => {
    // ...
  });
});
```

- **Repeating Setup For Many Test**: If you have some work you need to do repeatedly for many tests, you can use `test.beforeEach` and `test.afterEach`.

For example, let's say that several tests needs to authenticate to the test environment. You have a method ensureAuthenticated() that must be called before each of these tests, and a method clearDatabase() that must be called after each of these tests. You can do this with:

```ts
test.beforeEach(async ({ page }, testInfo) => {
  ensureAuthenticated();
});

test.afterEach(async ({ page }, testInfo) => {
  clearDatabase();
});
```

- **One-Time Setup**: In some cases, you only need to do setup once, at the beginning of a file. This can be especially bothersome when the setup is asynchronous, so you can't do it inline. Jest provides `test.beforeAll` and `test.afterAll` to handle this situation.

```ts
test.beforeAll(async () => {
  console.log('Before tests');
});

test.afterAll(async () => {
  console.log('After tests');
});
```

- Use a test function `test` to declare tests and expect function to write assertions.

```ts
test('one', async ({ page }) => {
  // ...
});
```

 - Use `test.step` in the test to represent various test scenarios in the [TestRun].

```ts
await test.step('Launch and Authenticate MakerShell', async () => {
    await makerPage.goToMakerPage();
});
```

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