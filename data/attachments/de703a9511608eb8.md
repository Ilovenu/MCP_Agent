# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: ui/contact/contact-form.spec.ts >> Contact us >> submits the contact form successfully @smoke
- Location: tests/ui/contact/contact-form.spec.ts:4:3

# Error details

```
Error: expect(locator).toBeVisible() failed

Locator: locator('h2').filter({ hasText: 'Get In Touch' })
Expected: visible
Timeout: 5000ms
Error: element(s) not found

Call log:
  - Expect "toBeVisible" with timeout 5000ms
  - waiting for locator('h2').filter({ hasText: 'Get In Touch' })

```

```yaml
- text: Please wait while your request is being verified...
```

# Test source

```ts
  1  | import { test, expect } from '../../../src/fixtures/test-options';
  2  | 
  3  | test.describe('Contact us', () => {
  4  |   test('submits the contact form successfully @smoke', async ({ contactUsPage }) => {
  5  |     await contactUsPage.open();
> 6  |     await expect(contactUsPage.getInTouchHeading).toBeVisible();
     |                                                   ^ Error: expect(locator).toBeVisible() failed
  7  | 
  8  |     await contactUsPage.fillForm(
  9  |       'QA Contact',
  10 |       'qa.contact@example.com',
  11 |       'Automated framework showcase',
  12 |       'This message was submitted by an automated Playwright test.',
  13 |     );
  14 |     await contactUsPage.submit();
  15 | 
  16 |     await expect(contactUsPage.successMessage).toBeVisible();
  17 |     await expect(contactUsPage.successMessage).toHaveText(
  18 |       'Success! Your details have been submitted successfully.',
  19 |     );
  20 |   });
  21 | });
  22 | 
```