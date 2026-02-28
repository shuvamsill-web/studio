# Favicon Setup Guide

## 📁 Required Favicon Files

To complete your favicon setup, add these image files to the `/public` folder:

### Essential Files (Minimum Required)
- **`favicon.ico`** - 16x16 or 32x32 ICO format (legacy browsers)
- **`favicon-16x16.png`** - 16x16 PNG
- **`favicon-32x32.png`** - 32x32 PNG
- **`apple-touch-icon.png`** - 180x180 PNG (iOS home screen icon)

### Recommended Additional Files
- **`android-chrome-192x192.png`** - 192x192 PNG (Android devices)
- **`android-chrome-512x512.png`** - 512x512 PNG (Android splash screen)
- **`safari-pinned-tab.svg`** - SVG format (Safari pinned tabs)
- **`mstile-150x150.png`** - 150x150 PNG (Windows 8/10 tiles)
- **`og-image.png`** - 1200x630 PNG (social media share image)

## 🎨 How to Generate Favicon Files

### Option 1: Online Generator (Easiest)
1. Visit **[favicon.io](https://favicon.io/)** or **[realfavicongenerator.net](https://realfavicongenerator.net/)**
2. Upload your logo/icon (ideally 512x512 or larger, square)
3. Download the generated favicon package
4. Extract and copy all files to `/public` folder

### Option 2: Design Software
1. Create a **512x512px** square image in your design tool (Figma, Photoshop, etc.)
2. Export multiple sizes:
   - 16x16, 32x32, 180x180, 192x192, 512x512 as PNG
   - Optional: SVG version for safari-pinned-tab
3. Convert largest PNG to ICO format using online converter
4. Name files according to list above
5. Place in `/public` folder

### Option 3: Command Line (ImageMagick)
```bash
# Install ImageMagick first
# Then run from your project root:

# From 512x512 source image:
convert logo-512.png -resize 16x16 public/favicon-16x16.png
convert logo-512.png -resize 32x32 public/favicon-32x32.png
convert logo-512.png -resize 180x180 public/apple-touch-icon.png
convert logo-512.png -resize 192x192 public/android-chrome-192x192.png
convert logo-512.png -resize 512x512 public/android-chrome-512x512.png
convert logo-512.png public/favicon.ico
```

## ✅ Current Configuration Status

Your site is already configured with:
- ✅ `index.html` with proper favicon links
- ✅ `site.webmanifest` for PWA support
- ✅ `browserconfig.xml` for Windows tiles
- ✅ Dynamic favicon loading from `siteConfig.ts`
- ✅ Theme color support (light/dark mode)
- ✅ Social media meta tags (Open Graph, Twitter)

**All you need to do is add the actual image files!**

## 🔧 Customizing Favicon Path

To use a different favicon location, edit `/src/app/data/siteConfig.ts`:

```typescript
export const siteConfig: SiteConfig = {
  siteName: 'Your Studio Name',
  tagline: 'Your Tagline',
  faviconPath: '/logo.png', // Change this to your file path
};
```

The favicon will automatically update in:
- Browser tabs
- Bookmarks
- Mobile home screens
- Site header logo

## 📱 Testing Your Favicon

After adding files, test on:
1. **Desktop browsers** - Chrome, Firefox, Safari, Edge
2. **Mobile devices** - iOS Safari, Chrome for Android
3. **PWA** - Add to home screen on mobile
4. **Social sharing** - Share a link on Twitter, Facebook, Slack

### Quick Test Checklist
- [ ] Favicon appears in browser tab
- [ ] Correct icon shows in bookmarks
- [ ] iOS "Add to Home Screen" shows proper icon
- [ ] Android "Add to Home Screen" shows proper icon
- [ ] Link previews show og-image on social media

## 🎯 Design Tips

1. **Keep it simple** - Favicons are tiny, avoid complex details
2. **High contrast** - Works well on both light and dark backgrounds
3. **Square format** - All favicon sizes are square
4. **Test at small sizes** - View your 16x16 version to ensure recognizability
5. **Brand consistency** - Use colors from your brand palette

## 🔄 Updating Your Favicon

When you update favicon files:
1. Replace the image files in `/public`
2. Keep the same filenames OR update `siteConfig.ts`
3. Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
4. Rebuild and redeploy: `npm run build`

## 📚 File Purpose Reference

| File | Size | Purpose |
|------|------|---------|
| `favicon.ico` | 16/32 | Legacy browser support |
| `favicon-16x16.png` | 16x16 | Modern browsers (small) |
| `favicon-32x32.png` | 32x32 | Modern browsers (medium) |
| `apple-touch-icon.png` | 180x180 | iOS devices |
| `android-chrome-192x192.png` | 192x192 | Android devices |
| `android-chrome-512x512.png` | 512x512 | Android splash screen |
| `safari-pinned-tab.svg` | Vector | Safari pinned tabs |
| `mstile-150x150.png` | 150x150 | Windows tiles |
| `og-image.png` | 1200x630 | Social media shares |

## 🚀 Quick Start (Copy & Paste)

**Don't have a logo yet?** Use a temporary placeholder:

1. Create a simple colored square (512x512) with your initials
2. Name it `favicon.png`
3. Update `siteConfig.ts`:
```typescript
faviconPath: '/favicon.png'
```
4. Add the same file with all required names to `/public`

You can always replace with professional icons later!
