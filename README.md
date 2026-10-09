# PanelFlow Sources

A ready-to-upload public JSON catalogue for the existing PanelFlow reader.
It contains one series, four chapters and 24 complete volleyball page images.
Panel and cover dimensions match the actual image files.

## Upload from Windows

1. Download PanelFlow_GitHub_Upload.zip and right-click it -> Extract All.
2. Open the extracted folder. Find catalogue.json, panelflow-repo.json,
   index.html, README.md and the media folder.
3. Open https://github.com/kleoslick-cmd/panelflow-extensions.
4. Click Add file -> Upload files.
5. Drag those four files AND the media folder into the upload area. Upload the
   contents, not the ZIP or its enclosing folder. Keep media/uploads intact.
6. Enter the commit message "Add PanelFlow catalogue and artwork", select the
   option to commit directly to main, then confirm the commit.

## Enable GitHub Pages

Settings -> Pages -> Source: Deploy from a branch -> Branch: main -> /(root)
-> Save. Wait for the Pages deployment to succeed (see the Actions tab).

Catalogue URL:
https://kleoslick-cmd.github.io/panelflow-extensions/catalogue.json

Test image URL:
https://kleoslick-cmd.github.io/panelflow-extensions/media/uploads/0379-018.jpg

## Connect the existing app

Open PanelFlow -> Browse -> Extensions -> PanelFlow JSON. Press Install if
needed, paste the catalogue URL above, and press Connect. Open Sources, choose
PanelFlow volleyball panels, and read the chapters. Connection caches the
catalogue metadata. Use Download Chapter to save artwork for offline reading.

The file panelflow-repo.json uses a PROPOSED PanelFlow repository manifest
format. Adding it to GitHub does not add repository support to the app. The
current connector accepts catalogue.json; repository discovery and adapter
installation are a separate implementation stage.

## Artwork and movement

This catalogue reuses the supplied complete pages with the existing gentle pan
and zoom presets, preserving full images and speech bubbles. It does not export
or install the app's authored character rigs. The animations that follow scroll
progress remain available in the existing reader. Device reduced motion and
Off mode show complete static panels.

## Edit or add content

Edit catalogue.json in VS Code. Preserve stable series, chapter and panel IDs.
Add each new chapter ID to the series' ordered chapterIds list. Number panel
orders consecutively starting at 1. Use the actual image pixel dimensions and
relative image paths, such as media/uploads/my-page.jpg. Upload every referenced
image. Increase a chapter's revision when its content, ordering or animation
changes. Change the image filename too when replacing its bytes. Increase the
catalogue version and use Refresh catalogue in PanelFlow after publishing.

## Verification performed before packaging

All 24 referenced artwork files were found, decoded and checked against their
metadata dimensions. The catalogue was checked with the current PanelFlow
validator and connector using a local HTTP server. ZIP contents and image
hashes were checked against the originals. GitHub hosting, actual cross-origin
access, touch scrolling and offline phone reading need testing after upload.
