# MOC — Accounts by Stage

All accounts grouped by stage. Hit `#active` only.

## Negotiation
```dataview
TABLE company, amount, next_action_date, last_touch
FROM "10_Accounts"
WHERE stage = "negotiation" AND contains(tags, "active")
SORT next_action_date ASC
```

## POC / Scoping
```dataview
TABLE company, amount, next_action_date, last_touch
FROM "10_Accounts"
WHERE (stage = "poc" OR stage = "scoping") AND contains(tags, "active")
SORT next_action_date ASC
```

## Discovery
```dataview
TABLE company, amount, next_action_date, last_touch
FROM "10_Accounts"
WHERE stage = "discovery" AND contains(tags, "active")
SORT next_action_date ASC
```

## Dormant (no touch >30 days)
```dataview
TABLE company, last_touch
FROM "10_Accounts"
WHERE contains(tags, "dormant")
SORT last_touch DESC
```
