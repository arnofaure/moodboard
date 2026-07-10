# Changelog

All notable changes to Moodboard are documented here.

## [0.10] - 2026-07-10

### Added
- Real app logo in the menu button (inline SVG, adapts to all 4 themes via `currentColor`), favicons, `manifest.json`, and Open Graph / Twitter card meta tags, matching Storyboard's setup.

### Changed
- The random picsum.photos seed images were replaced with ones actually checked by hand per category (Characters/Sets/Textures) instead of arbitrary stock photos.
- The default "Colors" category now seeds flat hex swatches generated the same way as the manual "+ Color" tool, instead of photos.

## [0.9] - 2026-07-09

### Fixed
- The lightbox side panel (tags, notes, palette, actions) used translucent white-overlay backgrounds that let the dark backdrop show through; switched to solid colors so it reads as a proper opaque panel.

## [0.8] - 2026-07-09

### Added
- Page footer, a Help guide modal (Menu → Help), and menu links to the Storyboard, Blocking, and Time Tracker apps plus GitHub — matching Storyboard's menu structure and footer.

### Changed
- Export now always captures the whole moodboard (every category, uncollapsed, unfiltered) instead of whatever partial or filtered view happened to be on screen.
- The Starred filter button uses a yellow active state instead of the blue used elsewhere.
- Removed the per-category colored top-border accent — it read as noisier than useful.
- Redesigned the lightbox layout: image and side panel are now centered as a group with equal margins, instead of the image stretching to fill space and pushing the panel against the window edge.

### Added
- `S` keyboard shortcut to star the image currently open in the lightbox (alongside the existing `W` for Wall view and `Cmd/Ctrl+S` for Save).

## [0.7] - 2026-07-09

### Added
- Auto-name colors from the nearest CSS/SVG named color (~140 standard names, matched by RGB distance) whenever the name field is left blank — applies to both manually added swatches and extracted palettes.

## [0.6] - 2026-07-09

### Added
- Manual color swatch creation: enter a hex or RGB value (plus an optional name) via "+ Color" in any category to add a flat color tile, instead of only extracting colors from existing images.

## [0.5] - 2026-07-09

### Added
- Toolbar rebuilt in Storyboard's style: logo button doubles as the menu trigger (Open/Save/New/Delete project, Help), with bigger icon+label buttons for Wall view and Starred filter, plus keyboard shortcut hints.
- Save/Open a project as a single JSON file (`Cmd/Ctrl+S` to save), so a project can be backed up or moved to another browser/device.
- Category drag-reorder via a dedicated handle, and collapsed categories now show as small thumbnail cards (like the project switcher) instead of a bare header line.
- Starred favorites, with a filter to show only starred images.

### Fixed
- Clicking an image never opened the lightbox: the thumbnail `<img>` had `pointer-events: none`, so it could never receive the click in the first place.
- The "Drop your images here" banner could get stuck visible after an internal drag-and-drop reorder, because the drag-counter logic didn't reset symmetrically for non-file drags.
- Color extraction silently failed for most images: re-fetching the same URL for a fresh CORS-enabled read could hit the browser's cache of the original (non-CORS) request and taint the canvas. Now re-fetched explicitly as a blob first.

## [0.4] - 2026-07-09

### Added
- Multi-select (shift/cmd-click or the corner checkbox) with a floating bar to bulk move, tag, or delete.
- Notes field per image, shown in the lightbox.
- Color palette extraction: pull 5 dominant colors from any image, attached directly to it and shown as a strip on its thumbnail and in the lightbox.
- Export the current view as a PNG image.
- Project switcher shows a mini thumbnail collage per project instead of plain text.

## [0.3] - 2026-07-09

### Added
- Tags and free-text search across tags and category names.
- "Wall" view: every image at its real aspect ratio instead of a cropped square, mixed across all categories or focused on just one expanded category.

## [0.2] - 2026-07-09

### Added
- Expand any category to a full-page view (⤢).

## [0.1] - 2026-07-09

### Added
- First release: categories with drag & drop, paste-from-clipboard/URL, and file-picker image import; a lightbox viewer; four background themes; everything stored locally in the browser via IndexedDB.
