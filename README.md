# Filter Bloat

uBlock Origin filter list that removes page bloat: unused panels, integrations and widgets that slow sites down.

## Subscribe

uBlock Origin → Dashboard → Filter lists → Import, then add:

```
https://raw.githubusercontent.com/ndewing-equinix/filter-bloat/main/dist/filter-bloat.txt
```

## Contributing

- Add rules to `filters/<vendor>.txt`, one comment per rule naming what it hides.
- Anchor on stable attributes (`data-testid`, `aria-label`) or visible text (`:has-text()`). Avoid hashed class names and `nth-of-type`.
- Prefer network rules (`||host/path$script`) when the bloat loads its own scripts or frames; hiding alone doesn't save the work.
- Run `mise run build` and commit `dist/`.
