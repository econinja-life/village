A **report** is a full description of the impact of a **product**. It includes an aggregated score, detailed descriptions, and samurai added data like comments, alternatives, and benefits (animals)

## Formulaic Factors
- `(score * weight) = $score`
- `( (negative score * weight) + (postive score * weight) ) = $score`, this CAN equal out to 0
- Positive factors can mitigate individual negative scores (like palm oil, but not 100% sustainable)
- Final category scores are averaged into one Product score

```
+(+7*3)          // Positive for producer uses sustainable palm oil - 70%
+(+10*4)        // Positive for partially recyclable packaging
+
    (
        (-10*3) // Negative for product contains palm oil
        +
        (+7*4)  // Positive for 70% sustainable palm oil (two would cancel out if 100% sustainable, and even gain some more points)
    )
+(-7*4)         // Negative for some other producer negative practice
```

## Json Representation
```javascript
{
    "meta": {
        "request": {},
        "user": {}
        "history":{
            "last-modified": "",
            "first-created": "",
            "trace-id": ""
        }
    },
    "ids": {
        "uuid": "/reports/ika9a732kq879797a2k"
        "system-id": "ika9a732kq879797a2k"
        "upc": 1771649028401912
    },
    "components": {},
    "processes": {},
    "producers": {},
    "positive": {
        175: "Graze uses 70% Sustainable Palm oil.",
        731: "Packaging is, at least, partially recyclable."
    },
    "negative": {
        639: "Palm oil is included -- and not from 100% sustainable sources",
        118: "Market Cool, one of the producers of an ingredient in this product, has been known to *do something bad*",
    },
    "scores": {
        "aggregate": 9 // out of 10
        "producer":{
            "overall": 771,
            "specific1": 11,
            "specific2": 3187
        }
    },
    "alternatives": {
        "<upc>": "Some Cool Alternative"
        "<upc>": "Some Other Alternative"
    },
    "content": {
        "comments": {},
        "notes": {},
        "articles": {},
        "rankings": {},
        "ratings": {}
    }
}
```