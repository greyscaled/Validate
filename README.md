# Validate

An incredibly simple, zero-dependency package for writing maintainable, easy-to-read, validation
assertions. This package is highly inspired by:

- The Java package [org.apache.commons.lang3.Validate][1]
- The native NodeJs module [`assert`][2]
- Matchers & BDD-style assertions used in [`Jest`][3] and [`chai`][4]

## Why Would I Use This

Usage of `Validate` is an opinionated, stylistic preference. Other options exists and can/should
be explored for the style that makes most sense for you/your team. The bottom line of this and
similar frameworks is to improve domain/logic expression and readability of source code.

## Example Usage

Without :x:

```ts
class PositiveNumber {
  public readonly value: number;

  constructor(i: number) {
    if (i <= 0) {
      throw new Error(`i must be greater than 0. Instead received ${i}`);
    }
    this.value = i;
  }
}
```

With :heavy_check_mark:

```ts
import { Validate } from '@vapurrmaid/validate';

class PositiveNumber {
  public readonly value: number;

  constructor(i: number) {
    Validate.isTrue(i > 0, `i must be greater than 0. Instead received ${i}`);
    this.value = i;
  }
}
```

[1]: https://commons.apache.org/proper/commons-lang/javadocs/api-3.1/org/apache/commons/lang3/Validate.html
[2]: https://nodejs.org/api/assert.html
[3]: https://jestjs.io/docs/en/using-matchers
[4]: https://www.chaijs.com/
