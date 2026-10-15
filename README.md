# World Flight Simulator — no-token build

A browser-based flight simulator prototype designed to deploy on Render without API keys.
The only custom configuration is the aircraft model URL in `static/app.js`.

## Render
- Build Command: `pip install -r requirements.txt`
- Start Command: `uvicorn main:app --host 0.0.0.0 --port $PORT`

No environment variables or tokens are required.

## Set the aircraft model
Open `static/app.js` and find `AIRCRAFT_MODEL_URL`. Paste a direct `.glb` or `.gltf` file URL.
The default is the raw GitHub URL for the Airbus A320 S7 model.
For GitHub, use `raw.githubusercontent.com/...`, not a `github.com/.../blob/...` page.

## Included
- 3D globe with OpenStreetMap imagery, no Cesium ion token
- aircraft model loaded directly from a URL, with fallback procedural aircraft if it fails
- chase/cockpit camera modes, keyboard and touch controls
- basic arcade flight physics, altitude/speed/heading HUD
- search for a place using the public Nominatim geocoder
- map, route destination and localStorage settings

This is a flight-sim prototype, not a certified navigation system. Terrain is a smooth globe (no token-gated terrain data). Public map/geocoder services have their own usage policies and rate limits.
