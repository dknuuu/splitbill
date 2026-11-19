# Split Bill

https://dknuuu.github.io/splitbill/

A tiny bill splitter. No account, no server.

Type who's at the table, what was ordered, and get a receipt showing what each person owes and why. Copy it as text, save, or share it as an image.

## Use it

- **Names:** everyone at the table, separated by commas.
- **Items:** one item per line, using the syntax below.
- **Done!:** The receipt updates as you type.

## Item syntax

Every line is `item price keyword`. The keyword must come right after the price.

| Line                           | Meaning                                  |
| ------------------------------ | ---------------------------------------- |
| `salmon 22 for Chloe`          | Charged to one person                    |
| `2 steak 56 for Andy, Bobby`   | Split between the people listed          |
| `3 beer 21 for Andy x2, Bobby` | Split by quantity (`x2` or `×2`; default is 1) |
| `salad 12 eq`                  | Split equally between everyone           |
| `discount -10 eq`              | A negative price is a discount           |
| `tax 7%`                       | A percentage of the bill, shared in proportion to what each person owes so far |
| `tip 20 prop`                  | A flat amount, shared in proportion to what each person owes so far |
| `tip 15% eq`                   | A percentage of the bill, split equally  |
| `paid by Bobby`                | Shown at the bottom. Everything after `paid by` is printed as typed, so you can add a bank or transfer number |

Notes:

- Names are not case sensitive, and a repeated name is ignored.
- A line that can't be read, or a name that isn't in the list, is flagged under the box with its line number instead of being silently ignored.
- Percentage and `prop` lines are applied after all the items, in the order you write them. Each percentage is worked out on the total so far, including earlier tax or tip lines.
- On a person's line the leading count is dropped from the item name (`2 steak` is shown as `Steak`), and the `x5` is kept, with the amount that person pays.
- An item whose name starts with `paid by` will be read as the payer line.

## Privacy

The only network requests are the font from Google Fonts and the Cloudflare Web Analytics page-view beacon. Your names and items are saved in localStorage, so they're remembered, and they never leave your device unless you copy or share the receipt yourself.

- **Google Fonts:** the font loads from Google's servers. When it loads, Google can see basic technical info about your visit, like your IP address and browser, as with any website that uses Google Fonts.
- **Cloudflare Web Analytics:** counts page views. According to Cloudflare, it doesn't use cookies or localStorage and doesn't fingerprint visitors. It records which page was loaded, never what you type into the app.

## License

MIT License. © 2026 dknuuu
