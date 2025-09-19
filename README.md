# Kolkata Durga Puja Map

A small, single-file interactive map showcasing Durga Puja pandals around Kolkata using Leaflet.

This project contains a single HTML file (`index.html`) that displays pandal locations, lets the user locate themselves, find nearest pandals, mark places as visited (persisted in `localStorage`), and provides UI niceties like animated markers, a sidebar list, and a nearest-results panel.

**Contents**
- `index.html` — The entire application (HTML, CSS, and JavaScript) in a single file.

**Features**
- Interactive Leaflet map with OpenStreetMap tiles.
- Predefined list of pandal locations (name, coordinates, and type/color).
- Locate yourself using the browser Geolocation API; displays a custom pulsing user marker.
- Calculate distances (Haversine) from the user to each pandal and sort the list.
- Find top nearest pandals and fit the map to show them together with your location.
- Mark pandals as "Visited"; visited state is stored in `localStorage` and reflected in the UI and marker color.
- Small UI conveniences: animated marker bounce/pulse, sidebar with place list, a legend, and a loading overlay.

Quick Preview
---------------
Open `index.html` in your browser (double-click or use a local static server). The app should load immediately.

Notes about location: the browser will prompt for permission when you click the "Locate" button. If permission is denied, the app shows helpful messages.

How to run locally
------------------
The file is static — no build step or server is strictly required. For best results (and to avoid some browsers blocking Geolocation or local resources when opened via `file://`), serve the folder using a small static server.
```

Usage
-----
- Click the "☰" menu button on small screens to open/close the sidebar.
- Click "📍 Locate" to request location permission and place a pulsing marker for your location.
- Click "🔍 Nearest" to show the top 3 nearest pandals; the map will fit bounds to show them and your location.
- Click the "Visit" button next to any pandal to mark it as visited. That state is saved in `localStorage` across sessions.
- Use the "Clear" button to reset visited state.

Customizing data
----------------
Pandal data lives in the `pujaLocations` array inside `index.html`. Each entry has this form:

```js
{ name: "Pandal Name", lat: 22.5, lng: 88.3, type: "red" }
```

- `name`: string shown in the list and popup
- `lat`, `lng`: numeric coordinates
- `type`: marker color used by `Leaflet.awesome-markers` (e.g., `red`, `blue`, `green`)

To add, remove, or update items, edit the array and refresh the page.

Dependencies
------------
All dependencies are loaded via CDN inside `index.html`:
- Leaflet (map)
- Leaflet.awesome-markers (marker icons)
- Font Awesome / Glyphicons (icons)

Troubleshooting
---------------
- If Geolocation fails or times out: check browser permissions and retry. Some browsers require served pages (http/https) for accurate geolocation.
- If markers or tiles don't load: make sure you have an internet connection because the app uses CDN-hosted libraries and OpenStreetMap tiles.

Next steps (suggested)
----------------------
- Add filtering (by area or type) and search.
- Persist additional metadata (photos, descriptions, visiting notes) in `localStorage` or a backend.
- Export/Share visited list as JSON or CSV.
- Improve accessibility labels and make the UI keyboard navigable.

License
-------
This is a small personal/static project. Reuse or adapt freely — optionally credit the original author.

Enjoy the map! 🎉