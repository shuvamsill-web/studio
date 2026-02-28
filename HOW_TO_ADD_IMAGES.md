# How to Add Your Own Images to the Gallery

## Step 1: Add Your Images

1. Place your image files (JPEG, PNG, etc.) in the `/public` folder
2. You can organize them in subfolders if you prefer (e.g., `/public/images/`, `/public/photos/`)

## Step 2: Update the Gallery Data

1. Open the file: `/src/app/data/gallery.ts`
2. Add your images to the `galleryItems` array

### Example:

```typescript
export const galleryItems: GalleryItem[] = [
  {
    id: '1',
    src: '/images/my-photo.jpg', // Path relative to /public folder
    title: 'My Artwork',
    subtitle: 'A beautiful painting I created',
    date: '2026-02-13', // Use YYYY-MM-DD format
    pinned: true // Optional: Set to true to keep at top
  },
  {
    id: '2',
    src: '/photos/sunset.png',
    title: 'Golden Sunset',
    subtitle: 'Captured at the beach',
    date: '2026-02-10'
  },
  // Add more items here...
];
```

## Required Fields:

- **id**: Must be unique for each image (e.g., '1', '2', '3')
- **src**: Path to your image file (starts with `/` and is relative to the `/public` folder)
- **title**: The main title shown when viewing the image
- **subtitle**: A caption or description
- **date**: Date in YYYY-MM-DD format (for chronological ordering, newest first)
- **pinned**: Optional - Set to `true` to keep this image at the top, or leave it out/set to `false`

## Chronological Ordering:

- Images are automatically sorted by date (newest first)
- Pinned items always appear at the top, regardless of date
- Multiple pinned items are sorted by date among themselves

## Supported Image Formats:

- JPEG (.jpg, .jpeg)
- PNG (.png)
- WebP (.webp)
- GIF (.gif)
- SVG (.svg)

## Tips:

- ✅ NO HARDCODING - Everything is controlled from `/src/app/data/gallery.ts`
- ✅ Simply drag and drop images to `/public` folder
- ✅ Update the data file with paths, titles, and subtitles
- ✅ Any aspect ratio works! The gallery automatically adjusts
- ✅ Desktop shows 3-4 columns, mobile shows 2 columns
- ✅ Use `pinned: true` for featured/important pieces
- For best performance, optimize your images before uploading