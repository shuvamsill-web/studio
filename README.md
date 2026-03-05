# Public Assets Folder

This folder contains static assets that are served directly by your website.

## How to Use Local Images

### For Avatar Image:
1. Place your avatar image in this folder (e.g., `avatar.jpg`, `avatar.png`, `avatar.svg`, etc.)
2. In `/src/content/links.ts`, update the avatar path:
   ```typescript
   avatar: "/avatar.jpg"  // Supports: .jpg, .png, .svg, .gif, .webp, etc.
   ```

**✅ SVG Support:** Yes! Avatar fully supports SVG images. Just use `avatar: "/avatar.svg"`

### For Favicon:
Place your favicon files in this folder:
- **`favicon.ico`** - Classic .ico format (recommended: 32x32 or 16x16)
- **`favicon.png`** - Modern PNG format (recommended: 32x32 or 192x192)
- **`favicon.svg`** - Scalable vector format (fully supported!)
- **`apple-touch-icon.png`** - iOS home screen icon (recommended: 180x180)

The site automatically loads `/favicon.ico` and `/apple-touch-icon.png` - just drop your files here!

### For Open Graph Image (Social Media Previews):
1. Place your OG image here (recommended size: 1200x630px)
2. In `/src/content/links.ts`, update the ogImage path:
   ```typescript
   ogImage: "/og-image.jpg"
   ```

## Important Notes:

- ✅ File paths start with `/` (e.g., `/avatar.jpg`, `/favicon.svg`)
- ✅ Files in this folder are publicly accessible
- ✅ No import needed - just reference the path as a string
- ✅ **Full SVG support** for avatar, favicon, and all images
- ✅ Supports: JPG, PNG, GIF, **SVG**, WebP, ICO, etc.

## Example Structure:
```
/public/
  ├── avatar.svg          (your profile picture - SVG supported!)
  ├── favicon.ico         (classic favicon)
  ├── favicon.svg         (modern scalable favicon)
  ├── apple-touch-icon.png (iOS icon - 180x180)
  ├── og-image.jpg        (social media preview image - 1200x630)
  └── README.md           (this file)
```

That's it! The system automatically reads whatever path you specify in `/src/content/links.ts` - completely dynamic, no hardcoding required.