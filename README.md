# Fiore-Filigrane

A product configurator and proforma builder for the **Fiore Rubinetterie Filigrane** collection, based on the *Listino Filigrane 09/26* price list.

Open `index.html` in a browser, or publish the repo with GitHub Pages. Nothing needs to be built or installed.

## What it does

1. **Configure a product** step by step, with large dropdowns and catalogue photo tiles:
   product family → model → version → body finish → handle style → handle finish → code option → quantity.
2. **Builds the full product code and list price** live, for example `540CRRLP5230S1 01`.
3. **Collects lines into a proforma** with client and seller details, quantities, line discounts, an extra discount, VAT (24% by default) and totals.
4. **Exports a PDF** (A4, with product photos and Greek text) and helps send it by WhatsApp or email (Gmail).
   Links cannot attach files, so the PDF is saved first and then attached by hand.

## Catalogue coverage

| Family | Models |
|---|---|
| Basin & bidet mixers | 5230 basin, 5240 medium basin, 5250 tall basin, 5255 bidet, 5440 3-hole basin |
| Wall basin mixers (external parts) | P9567, P9537, P9597, P9587 |
| Built-in shower mixers (external parts) | P7101 / P7201, P7103 / P7203 |
| Easy K-Box built-in bodies | 35AC5001, 35AC5002, 35AC5003, 35AC5004 |
| Showers, spouts & wastes | 30CR8680, 30CR8786, 30CR8758, 30CR8751, 30CR8857 |

**Handle styles:** 540 Jersey, 541 Piqué, 542 Denim, 543 Flow Line, 544 Flow, 545 Twill.

**Handle finishes (12):** CR Chrome, NN Matt black, AA Steel, GR Graphite, NLP Shiny Gun Metal, NSP Brushed Gun Metal, BSP Brushed Copper Bronze, RSP Brushed Copper, BLP Shiny Copper Bronze, RLP Shiny Copper, OSP Brushed Titanium Gold, OLP Shiny Titanium Gold.

**Body finishes:** CR Chrome, NN Matt black.

### Code structure

```
540  CR  RLP  5230  S1  01
│    │   │    │     │   └─ code option (01 / 02, where the price list has it)
│    │   │    │     └──── version (S1 = flat spout)
│    │   │    └────────── model
│    │   └─────────────── handle finish (replaces XXX)
│    └─────────────────── body finish
└──────────────────────── handle style
```

## Files

- `index.html`: the whole app in one file. It includes the HTML, CSS and JavaScript, the product, handle, finish and catalogue photos from the price list, and the DejaVu Sans font subsets (Latin and Greek) used in the PDF.

The PDF is generated with [jsPDF](https://github.com/parallax/jsPDF) and [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable), loaded from cdnjs.

## Notes

- Prices are list prices in euro, excluding VAT, from the 09/26 price list.
- Code option **02** is marked only with a ½ symbol in the price list; its meaning should be confirmed with Fiore.
- For the accessories the price list shows only the CR code, so matt black lines keep that code and name the NN finish in the description.
- Proforma lines and form fields are kept in the browser's local storage only.

---

Made by Ing. Dimitrios Skiadopoulos
