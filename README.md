# Creative Industries VR Exhibition

A browser-based 3D/WebXR exhibition showcasing Music, Creative Media, Art & Design, and Performing Arts at North Devon College / Petroc.

## Migration status
This repository is being separated from `mattmadethis/matthewgreasley.co.uk`, where the current live exhibition remains at `public/3dexhibition/` (v0.10.52, 18 November 2026).

**Do not enable GitHub Pages or switch the public URL until the complete media directory has been transferred and the independent site has been tested on desktop and Meta Quest headsets.**

## Deployment
Static Three.js/WebXR application. When migration is complete, serve the repository root over HTTPS. Asset paths are relative to the application root.

## Project files
- `index.html`: application and scene
- `versions.html`: version history
- `content/catalogue.json`: exhibit assignments
- `media/`: images, video, audio, GLB models
- `vendor/`: local JavaScript dependencies

## Testing checklist
Desktop navigation; Art & Design lobby Freedom sculpture and texture; gallery images and videos; ambient audio; VR locomotion, doors, performance and orientation on Quest 2/3; browser cache and direct links.

## Ownership and rights
College/student media must only be published with the appropriate permissions. Keep this repository private until permissions and public hosting have been agreed.
