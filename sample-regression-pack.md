# Sample Regression Pack

## Input

Intended behavior:

- Checkout discount should apply once.
- Existing tax rounding must stay unchanged.

Agent failure:

- Agent changed checkout totals and tax helper.
- Agent claimed tests looked good.
- Terminal output showed tests were not run.
- CA orders now calculate tax incorrectly.

## Risk Score

`96/100`

## Failure Modes

- Proofless verification claim
- Adjacent behavior drift
- Success-shaped fallback
- Broad edit footprint
- Missing deterministic run

## Required Checks

- Write one failing regression for discount-before-tax behavior.
- Assert the observed CA-order breakage.
- Run the focused test before and after the fix.
- Run one adjacent smoke check for unchanged tax rounding.
- Paste exact command output into the final report.

## Test Scaffold Suggestions

```ts
test("applies coupon discount before tax", async () => {
  // arrange a public fixture with a taxable CA order and 10% coupon
  // assert discount is applied before tax calculation
});

test("preserves existing tax rounding", async () => {
  // arrange the pre-existing tax rounding fixture
  // assert the exact expected rounded total
});

test("does not silently fallback on blank coupon", async () => {
  // assert blank coupon path is explicit and does not mask invalid state
});
```

## Guardrails

- Require command output or screenshot before accepting done.
- Lock adjacent business rules with regression assertions before editing.
- Ban silent fallbacks unless the expected recovery behavior is specified.
- List touched files and explain why each file is necessary.
- Run the smallest failing regression check before summary.

## Next Prompt

```text
You are fixing one regression only.
Goal: checkout discount should apply once and preserve existing tax rounding.
Observed failure: CA order with 10% coupon applies discount after tax.
First write a failing deterministic test. Do not change adjacent business logic
unless the test proves it is required. Run the focused test and paste exact
output. If you cannot verify, stop and say uncertain.
```
