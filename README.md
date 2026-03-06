# cinema-finder-poc-forked-
Created with CodeSandbox

# Cinema Finder - Bug Fix Submission

## Bugs Fixed

### Bug 1 - MapLibre Navigation Error
**File:** `src/components/Map/MaplibreMap.jsx`

**Problem:** When using MapLibre as the map library, clicking on a 
cinema in the list caused an unexpected error. The coordinates 
were being passed in the wrong order `[lat, lng]` but MapLibre 
expects `[lng, lat]`.

**Fix:** Swapped the coordinates in the `flyTo` function from 
`[lat, lng]` to `[lng, lat]`.

---

### Bug 2 - Limited Location Coverage
**File:** `src/components/Map/MaplibreMap.jsx`

**Problem:** The map allowed users to scroll anywhere in the world 
even though cinema data only exists for Australia and New Zealand. 
This was misleading for users outside these countries.

**Fix:** Added `maxBounds={convertBounds(totalBounds)}` to restrict 
map movement to Australia and New Zealand only, matching the 
available cinema data.

---

## How To Run

- `yarn install` to install dependencies
- `yarn start` to run the application
- `yarn build` to build for production
