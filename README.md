# TCG Images Repository

A GitHub Pages site for hosting Trading Card Game (TCG) images. This repository provides a centralized location for TCG card images that can be used in backend projects to generate CSV files for eBay's bulk upload tool.

## 🌐 Live Site

Visit the live site at: [https://gitwilldone.github.io/tcg-images.github.io](https://gitwilldone.github.io/tcg-images.github.io)

## 📁 Repository Structure

```
tcg-images.github.io/
├── index.html          # Main page displaying available images
├── manifest.json       # JSON file listing all available images
├── images/            # Directory containing all TCG card images
│   ├── README.md      # Documentation for image organization
│   └── example-set/   # Example directory (replace with actual sets)
└── README.md          # This file
```

## 🔗 Using Image URLs

All images are publicly accessible via the base URL:
```
https://gitwilldone.github.io/tcg-images.github.io/images/{set-name}/{image-name}.jpg
```

### Example URLs
```
https://gitwilldone.github.io/tcg-images.github.io/images/base-set/charizard.jpg
https://gitwilldone.github.io/tcg-images.github.io/images/fossil/dragonite.jpg
```

## 📝 Adding New Images

1. **Create a directory** for your TCG set if it doesn't exist:
   ```bash
   mkdir -p images/your-set-name
   ```

2. **Add your images** to the set directory following the naming convention:
   - Use lowercase with hyphens
   - Supported formats: `.jpg`, `.png`, `.webp`
   - Example: `charizard-holo.jpg`

3. **Update manifest.json** with your new images:
   ```json
   {
     "version": "1.0.0",
     "lastUpdated": "2026-01-29",
     "baseUrl": "https://gitwilldone.github.io/tcg-images.github.io",
     "images": [
       {
         "name": "Charizard Holo",
         "set": "base-set",
         "url": "https://gitwilldone.github.io/tcg-images.github.io/images/base-set/charizard-holo.jpg"
       }
     ]
   }
   ```

4. **Commit and push** your changes:
   ```bash
   git add .
   git commit -m "Add new TCG images"
   git push
   ```

## 🤖 Programmatic Access

### Manifest JSON

The `manifest.json` file provides a programmatic way to access all available images. It includes:
- Version information
- Last updated timestamp
- Base URL
- Array of all available images with metadata

Example usage in a backend application:
```javascript
fetch('https://gitwilldone.github.io/tcg-images.github.io/manifest.json')
  .then(response => response.json())
  .then(data => {
    // Generate CSV for eBay bulk upload
    const csv = data.images.map(img => 
      `${img.name},${img.set},${img.url}`
    ).join('\n');
  });
```

## 📦 eBay Bulk Upload Integration

The image URLs provided by this site can be directly used in eBay's bulk upload CSV files:

1. Access the manifest.json to get all image URLs
2. Generate a CSV file with product information and image URLs
3. Use the CSV with eBay's bulk listing tool

## 🛠️ Local Development

To test the site locally:

```bash
# Clone the repository
git clone https://github.com/GitWillDone/tcg-images.github.io.git
cd tcg-images.github.io

# Open index.html in your browser
# Or use a simple HTTP server:
python -m http.server 8000
# Then visit http://localhost:8000
```

## 📄 License

This repository is for hosting TCG card images for listing purposes.
