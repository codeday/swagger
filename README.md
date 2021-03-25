# swagger
Webapp to collect addresses and submit orders to shipstation 

# Features (aka to-do list for tyler)

- [ ] Sign in with CodeDay acconut
- [ ] Save last entered address (never automatically send anything, but ask "here's the address you gave us last time, is this still up to date?")
- [ ] Read a from a JWT or something to create a one-time-use link
- [ ] JWT contains json in shipstations order format
- [ ] cli tool/code samples for generating the links
- [ ] support for selecting from a dropdown for tshirt size (maybe we could define a schema of items to pass in a dropdown and it would automatically display it? my idea for an implementation below)

The way I see this working: 
pass it a jwt containing JSON like: 
```json
{
  "info": {
    "title": "CodeDay T-shirt and Lapel pin form",
    "details": "an optional description"
  },
  "items": [
    "sku": "SKU_FOR_PIN",
    "quantity": "1"
  ],
  "dropdowns": [
    {
      "title": "shirt size",
      "options": [
        {
        "label": "S",
        "sku": "SMALL_SHIRT_SKU",
        "quantity": 1
        },
        
        {
        "label": "M",
        "sku": "MEDIUM_SHIRT_SKU",
        "quantity": 1
        }
      ]
    }
  ]
}
```
