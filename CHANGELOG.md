# Changelog

All notable changes to Pallet Pilot will be documented in this file.

## [1.1.1] - 2026-02-05

### Fix

- **SKU extraction for manifest API** - Fixed bug where some auctions failed to download manifests with error "Nie znaleziono manifestu" (Manifest not found)
    - URLs like `spLc5OJ9JNK5032026` were incorrectly truncated to `spLc5OJ9` instead of `spLc5OJ9JNK`
    - Now scrapes actual SKU directly from page details (primary method)
    - Improved URL fallback: properly removes 7-digit batch codes (`5032026`) and 8-digit dates (`20260127`)

- **Extension context invalidation error** - Added graceful handling when extension is reloaded while page is open
    - Previously showed "Uncaught Error: Extension context invalidated"
    - Now silently handles the error and prompts user to refresh if needed

## [1.1.0] - 2026-02-04

### Added
- Cost per item calculation in FAB panel (bid price + shipping + VAT)
- Shipping cost tiers with automatic lookup based on pallet weight
- User-defined shipping cost overrides for PLN currency
- Fully customizable shipping tiers for GBP, EUR, and USD currencies
- "Exclude shipping" checkbox to calculate costs without shipping component
- Custom scrollbar styling in popup and FAB panel

## [1.0.1] - 2026-02-04

### Changed
- New pallet jack icon
- Removed debug console logs

## [1.0.0] - 2026-02-04

### Added
- Initial release
- Manifest analysis with product count, value, and category breakdown
- Floating Action Button (FAB) on supported auction pages
- Purchase tracking with custom prices
- Competitor watchlist for monitoring specific bidders
- Multi-language support (English, Polish)
- Theme options (Light, Dark, Auto)
- Local storage using IndexedDB
- Dashboard with quick stats and recent analyses
