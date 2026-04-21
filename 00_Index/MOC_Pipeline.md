# MOC — Pipeline by MEDDPICC Completeness

The deals at risk are the deals with missing slots. This is the health check.

## All active deals
```dataview
TABLE stage, amount, next_action_date, last_touch
FROM "10_Accounts"
WHERE contains(tags, "active")
SORT amount DESC
```

## Missing economic buyer
```dataview
LIST
FROM "10_Accounts"
WHERE contains(tags, "active") AND (!economic_buyer OR economic_buyer = "")
```

## Missing champion
```dataview
LIST
FROM "10_Accounts"
WHERE contains(tags, "active") AND (!champion OR champion = "")
```

## Missing paper process
```dataview
LIST
FROM "10_Accounts"
WHERE contains(tags, "active") AND (!paper_process OR paper_process = "")
```

## Missing metrics
```dataview
LIST
FROM "10_Accounts"
WHERE contains(tags, "active") AND (!metrics OR metrics = "")
```
