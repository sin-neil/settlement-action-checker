# Settlement Action Checker

An interactive reference tool for Xenith operators to quickly determine which actions are available for a settlement based on its current Transaction Status, API Status, and Settlement Type.

## What it does

The checker filters the live UI-valid state combinations and surfaces only the actions an operator can actually take — eliminating guesswork from the settlement workflow.

## How to use

1. Select **Transaction Status** (Pending, Processing, Success, Cancelled).
2. Select **API Status** — options are dynamically filtered to match live UI behavior.
3. Select **Settlement Type** (Same Currency or International).
4. The tool displays the available actions in the order they appear in the Xenith dashboard.

## State coverage

| Transaction Status | API Status | Settlement Type | Available Actions |
|:---|:---|:---|:---|
| Pending | No API Status | Both | Approve, Cancel |
| Processing | No API Status | Same Currency | Submit API, Mark as Success, Cancel |
| Processing | API Processing | Both | Awaiting gateway response |
| Processing | API Failed | Same Currency | Submit API, Mark as Success, Cancel |
| Processing | Name Mismatch | Same Currency | Submit API, Mark as Success, Cancel |
| Processing | Non Definitive | Both | Awaiting gateway response |
| Processing | No API Status / API Failed / Name Mismatch | International | Mark as Success, Cancel |
| Success | No API Status | International | Upload Payment Proof |
| Success | Any | Same Currency | None |
| Cancelled | Any | Both | None |

## Cost behavior reference

| Mechanism | Fee Configuration Used |
|:---|:---|
| Submit API | Payout & API Settlement |
| Mark as Success | Manual Same Currency Settlement |

## Deployment

This page is deployed via [GitHub Pages](https://pages.github.com/).

## License

MIT
