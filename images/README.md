# Image Directory

This directory contains TCG card images organized by set.

## Directory Structure

Each subdirectory represents a different TCG set:
- `example-set/` - Example set (replace with actual set names)

## Naming Convention

Images should follow this naming convention:
- Use lowercase with hyphens for card names
- Use `.jpg`, `.png`, or `.webp` format
- Example: `charizard-holo.jpg`

## Adding New Images

1. Create a new directory for the set if it doesn't exist
2. Add your images to the appropriate set directory
3. Update the `manifest.json` file in the root directory
4. Commit and push your changes

The images will be accessible at:
`https://gitwilldone.github.io/tcg-images.github.io/images/{set-name}/{image-name}.jpg`
