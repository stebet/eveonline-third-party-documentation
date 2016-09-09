# Loyalty Point Store

The loyaltystore resource allows an application to read information on the loyalty point store for a corporation.

### Route
``/corporations/<corporationID:corporationIdType>/loyaltystore/``


### API version

LoyaltyStoreOffersCollection-v1+json

### GET
* Cache: 1 hour
* example below: [https://crest-tq.eveonline.com/corporations/1000004/loyaltystore/](https://crest-tq.eveonline.com/corporations/1000004/loyaltystore/)

```json
{
  "totalCount_str": "151",
  "items": [
    {
      "iskCost": 65000000,
      "lpCost_str": "65000",
      "iskCost_str": "65000000",
      "requiredItems": [],
      "lpCost": 65000,
      "item": {
        "id_str": "10226",
        "href": "https://crest-tq.eveonline.com/inventory/types/10226/",
        "id": 10226,
        "name": "Social Adaptation Chip - Improved"
      },
      "id_str": "3437",
      "quantity_str": "1",
      "id": 3437,
      "quantity": 1
    },
    {
      "iskCost": 0,
      "lpCost_str": "250000",
      "iskCost_str": "0",
      "requiredItems": [
        {
          "item": {
            "id_str": "24698",
            "href": "https://crest-tq.eveonline.com/inventory/types/24698/",
            "id": 24698,
            "name": "Drake"
          },
          "quantity_str": "1",
          "quantity": 1
        },
        {
          "item": {
            "id_str": "17646",
            "href": "https://crest-tq.eveonline.com/inventory/types/17646/",
            "id": 17646,
            "name": "Caldari CU-1 Nexus Chip"
          },
          "quantity_str": "2",
          "quantity": 2
        }
      ],
      "lpCost": 250000,
      "item": {
        "id_str": "33153",
        "href": "https://crest-tq.eveonline.com/inventory/types/33153/",
        "id": 33153,
        "name": "Drake Navy Issue"
      },
      "id_str": "15779",
      "quantity_str": "1",
      "id": 15779,
      "quantity": 1
    },
    { "..." },
    { "..." },
    { "..." }
  ],
  "pageCount": 1,
  "pageCount_str": "1",
  "totalCount": 151
}
```