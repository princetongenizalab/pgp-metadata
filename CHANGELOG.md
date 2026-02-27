# Change log for Geniza dataset

## Version 1.1, February 2026

### Data changes

- Total 35,855 documents (+661)
- Total 36,172 fragments (+564)
- Total 712 sources (+33)
- Total 24,412 footnotes (+850)
- Total 1,802 people (+469)
- Total 486 places (+77)

### Structural changes

- fragments:
   - renamed `old_shelfmark` to `shelfmark_historic`
   - 3 new fields: `provenance`, `provenance_display`, `material_support`
- sources: 2 new fields: `citation`, `slug`
- footnotes: 1 new field `source_slug`
- people: renamed `occasional_trips_to` to `traveled_to`
- places: 2 new fields: `is_region`, `geographic_area`

## Version 1.0, July 2025

- Total 35,194 documents
- Total 35,608 fragments
- Total 679 sources
- Total 23,562 footnotes
- Total 1,333 people
- Total 409 places