# Renderer Selection

## Default Recommendation

Prefer HTML/CSS plus a paged-media renderer when the report must feel premium, heavily branded, and publication-quality.

This path is usually best for:

- precise typography
- print-aware spacing
- cover pages
- repeating header or footer patterns
- internal TOC links
- bookmark-friendly heading structure
- flexible table and chart styling

## Use an Existing House Pipeline When

- the repository already has a proven PDF generator
- the organization requires a specific rendering path
- the template system is already established
- the output quality is already strong

Adapt the skill to the house pipeline instead of fighting it.

## Use Native PDF Libraries When

- the layout is simple
- the environment cannot support browser or paged rendering
- the report is mostly tabular or form-like
- precise editorial styling is less important than deterministic programmatic output

## Decision Guide

| Constraint | Best choice |
| --- | --- |
| premium visual design | HTML/CSS + paged media |
| existing mature PDF stack | existing stack |
| simple machine-generated output | native PDF library |
| many charts and polished layouts | HTML/CSS + paged media |
| strict environment limitation | whatever the runtime can support reliably |

## Navigation Notes

- A visual TOC is not the same as PDF bookmarks.
- Internal anchor links improve navigation inside the document.
- Bookmark support depends on the renderer, so verify it after export.
- Keep heading levels consistent so bookmarks are readable.

## Graceful Degradation

If the renderer cannot support a feature cleanly:

- keep the visible TOC even if bookmarks are limited
- keep the footer text even if advanced margin boxes are unavailable
- render a clean table instead of a weak chart
- simplify layout before sacrificing readability
