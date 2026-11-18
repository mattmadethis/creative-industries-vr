# Automatic exhibition population

Upload your own or individually selected, licensed images to the department and room folder here. Example: music/room-03/photo.jpg.

Run the **Populate Exhibition** GitHub Actions workflow on main. Select all departments and room 0 to process every folder, or choose a specific department and room. The script optimises local uploads to WebP (maximum 1600 pixels on the long edge), assigns only empty frames, and preserves existing catalogue assignments. Original uploads remain unchanged. Use filenames that describe the artwork; titles are derived from filenames. Review catalogue metadata before publishing student work.

For Pixabay, select individual images on Pixabay and supply their numeric image IDs in the workflow input, maximum six in a single selected room. The API key is read from the repository secret. Search metadata is cached for 24 hours. Attribution and source links are preserved. The workflow does not perform mass downloads or hotlink images. Review the Pixabay Content License and obtain any additional rights needed for depicted people or third-party works.

After a successful run, manually run the live deployment workflow. GitHub's default workflow token does not trigger other workflows from its commits. Existing artwork is never overwritten by this importer.

## Stress testing

Select stress_test = fill to reuse existing local sample photographs in any unoccupied frames. Select clear to remove only temporary stress-test assignments. Normal uploaded or curated images can replace temporary assignments automatically; permanent assignments are preserved. No extra Pixabay requests or duplicate files are made in stress-test mode. Reused images may be served from browser cache, so this tests decoded texture and rendering load more than unique-file network throughput.

### Unique-file stress test

Select all departments, room 0, stress_test = unique, and leave Pixabay IDs blank. This generates deterministic WebP variants of the local sample images with unique paths per room and wall position, replacing temporary assignments only. With the original five photographs retained, the current full exhibition will use 125 derived files plus five originals, for 130 distinct image URLs. The workflow commits the generated files and catalogue together; no external downloads occur. Re-running is idempotent. Clear removes temporary assignments but retains generated assets on disk so they can be reused. Use a cold browser cache for first-visit network testing.
