# How to Add Your Brand Logo

## Step 1: Add Your Logo File

Place your logo image file in the `/home/z/my-project/public/` folder.

**Recommended formats:**
- **PNG** - Best for logos with transparency
- **SVG** - Perfect for scalability (if you have vector artwork)
- **JPG** - Use if no transparency needed

**Recommended filename:** `optitude-logo.png` or `optitude-logo.svg`

## Step 2: Update the Navigation Component

Edit `/home/z/my-project/src/components/optitude/Navigation.tsx`:

Find this section (around line 41-48):
```tsx
{/* OPTION 1: If you have an image logo, uncomment and use this: */}
{/*
<img
  src="/optitude-logo.png"
  alt="Optitude360 Logo"
  className="h-10 sm:h-12 w-auto"
/>
*/}

{/* OPTION 2: Text-based logo with icon (remove if using image logo) */}
<div className="flex items-center gap-3">
  <div className="w-10 h-10 sm:w-12 sm:h-12 bg-gold rounded-sm flex items-center justify-center">
    <span className="text-navy font-sans font-bold text-xl sm:text-2xl">O</span>
  </div>
  <div className="flex flex-col">
    <span className="font-sans font-semibold text-lg sm:text-xl text-white leading-tight">
      Optitude360
    </span>
    <span className="font-serif text-xs sm:text-sm text-gold/80 tracking-wider uppercase">
      Executive Search
    </span>
  </div>
</div>
```

**To use your image logo:**
1. Uncomment the `<img>` tag (remove the `/*` and `*/`)
2. Change the `src` to match your filename (e.g., `/my-logo.png`)
3. Update the `alt` text to your company name
4. Remove or comment out the "OPTION 2" text-based logo section

**Example after changes:**
```tsx
<img
  src="/optitude-logo.png"
  alt="Optitude360 Logo"
  className="h-10 sm:h-12 w-auto"
/>

{/* Text-based logo - REMOVED since we're using image logo */}
```

## Step 3: Update the Footer (Optional)

Edit `/home/z/my-project/src/app/page.tsx`:

Find this section (around line 80-89):
```tsx
{/* Logo - Uncomment and use your actual logo file */}
{/*
<div className="flex items-center gap-3 mb-6">
  <img
    src="/optitude-logo.png"
    alt="Optitude360 Logo"
    className="h-12 w-auto"
  />
</div>
*/}

{/* Text-based logo (remove if using image logo) */}
<div className="flex items-center gap-3 mb-6">
  <div className="w-10 h-10 bg-gold rounded-sm flex items-center justify-center">
    <span className="text-navy font-sans font-bold text-lg">O</span>
  </div>
  <span className="font-sans font-semibold text-xl">Optitude360</span>
</div>
```

**To use your image logo in the footer:**
1. Uncomment the `<img>` tag
2. Change the `src` to match your filename
3. Remove or comment out the text-based logo section

## Step 4: Adjust Logo Size (If Needed)

The size classes control your logo dimensions:

- **h-10** = 40px tall (mobile)
- **h-12** = 48px tall (desktop)
- **h-16** = 64px tall (larger)
- **w-auto** = Automatic width to maintain aspect ratio

**Examples:**
```tsx
<!-- Small logo -->
<img src="/logo.png" className="h-8 sm:h-10 w-auto" />

<!-- Medium logo (current) -->
<img src="/logo.png" className="h-10 sm:h-12 w-auto" />

<!-- Large logo -->
<img src="/logo.png" className="h-12 sm:h-16 w-auto" />
```

## Step 5: Test Your Logo

1. Save your changes
2. The dev server will automatically reload
3. Check the Preview Panel to see your logo
4. Verify it looks good on both mobile and desktop

## Tips for Best Results

✅ **Use PNG with transparency** for the best integration
✅ **Export at 2x or 3x resolution** for crisp display on retina screens
✅ **Keep the logo simple** - complex details may not be visible at small sizes
✅ **Test on both light and dark backgrounds** (your site has navy and off-white sections)
✅ **Ensure good contrast** between your logo and the background

## Need a Logo Variation?

If you need different logo versions for different backgrounds, you can use conditional rendering:

```tsx
{/* White logo for dark backgrounds */}
<img src="/optitude-logo-white.png" className="h-10 sm:h-12 w-auto dark:hidden" />

{/* Colored logo for light backgrounds */}
<img src="/optitude-logo.png" className="h-10 sm:h-12 w-auto hidden dark:block" />
```

---

**Questions?** The navigation header now appears on all pages with smooth scrolling to each section!
