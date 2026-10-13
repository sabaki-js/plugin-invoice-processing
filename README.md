# @sabaki-js/invoice-processing

Typed decisions over invoices, orders and deliveries (duplicate, match, disposition).

A [sabaki](https://github.com/sabaki-js/sabaki) plugin. Router keywords included:
register it and `Sabaki.decide()` routes matching states here automatically.

## Install

```sh
npm install @sabaki-js/invoice-processing sabaki
```

Zero runtime dependencies (bundled TF-IDF weights, 20 Ko).

## Usage

```ts
import { Sabaki } from "sabaki";
import mail from "@sabaki-js/invoice-processing";

const sabaki = new Sabaki();
sabaki.register(mail.default ?? mail);
const r = sabaki.decide({ state: "Votre facture mobile est disponible", question: "duplicate" });
// { domain: "invoice_processing", decision: ..., confidence: ..., plugin: "@sabaki-js/invoice-processing" }
```

Ask another question with `input.question` (any of the list below).


## Questions (measured on held-out test sets)

- `duplicate` — accuracy **0.890** (true/false)
- `matches_order` — accuracy **0.660** (true/false)
- `urgency` — accuracy **0.630** (1-3)
- `discrepancy_severity` — accuracy **0.550** (0-3)
- `disposition` — accuracy **0.520** (approve/hold/manual_review/reject)

Accuracies are honest test-split numbers, not marketing. See `sabaki` for the
`nano` / `mini` modes and the benchmark methodology.

## License

MIT
