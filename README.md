<img src="https://raw.githubusercontent.com/sabaki-js/sabaki/main/assets/logo.svg" width="120" alt="sabaki logo" />

# @sabaki-js/invoice-processing

[![npm](https://img.shields.io/npm/v/%40sabaki-js%2Finvoice-processing)](https://www.npmjs.com/package/%40sabaki-js%2Finvoice-processing) [![license](https://img.shields.io/npm/l/%40sabaki-js%2Finvoice-processing)](https://github.com/sabaki-js/plugin-invoice-processing#readme) [![CI](https://github.com/sabaki-js/plugin-invoice-processing/actions/workflows/test-battery.yml/badge.svg)](https://github.com/sabaki-js/plugin-invoice-processing/actions)

Invoice, order and delivery decisions.

Questions: `duplicate` (0.89), `matches_order` (0.66), `urgency` (0.63), `discrepancy_severity` (0.55), `disposition` (0.52). Weights: 20 KB.

## Usage

```ts
import { Sabaki } from "sabaki";
import plugin from "@sabaki-js/invoice-processing";

const sabaki = new Sabaki().register(plugin.default ?? plugin);
const r = sabaki.decide({ state: "..." });
// { domain: "invoice_processing", decision: ..., confidence: ..., plugin: "@sabaki-js/invoice-processing" }
```

Ask another question with `input.question`.

Part of [sabaki](https://github.com/sabaki-js/sabaki) - see the [GUIDE](https://github.com/sabaki-js/sabaki/blob/main/GUIDE.md).

## License

MIT
