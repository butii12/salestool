# Config Strategies

## Merge Rules

### Scalars
→ replace

### Objects
→ merge by key

### Lists
→ defined per config domain

---

## Domains

### KPI config
→ replace lists

### Dashboard config
→ merge widgets

### Feature config
→ replace

---

## Rule

Each config domain must define its merge behavior explicitly.