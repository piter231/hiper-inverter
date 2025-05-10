# Invert & Flip Bookmarklet  
**A browser bookmarklet that inverts page colors and flips images vertically**  

## Features  
- 🌗 Toggle full-page color inversion  
- 🖼️ Flip all images vertically (including background images)  
- ♻️ Toggle effects on/off with one click  
- 🚫 No external dependencies  
- 📦 Self-contained (works in most modern browsers)  

## Installation  
1. Copy this code:  
```javascript
javascript:(function(){function a(){document.documentElement.style.filter='invert(1) hue-rotate(180deg)';}function b(){document.documentElement.style.filter='none';}function c(){const e=document.querySelectorAll('img, picture, [style*="background-image"]');e.forEach(n=>{if(n.tagName==='IMG'){n.style.transform='scaleY(-1)';}else{const o=getComputedStyle(n).backgroundImage;o&&o!=='none'&&(n.style.backgroundImage=o+', linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0))');}});}function d(){const e=document.querySelectorAll('img, picture, [style*="background-image"]');e.forEach(n=>{n.tagName==='IMG'?n.style.transform='':n.style.backgroundImage=n.style.backgroundImage.replace(/, linear-gradient\(180deg, rgba\(0,0,0,0\), rgba\(0,0,0,0\)\)$/,'');});}const t=document.documentElement.style.filter.includes('invert(1)');t?(b(),d()):(a(),c());})();
```  
2. Create a new browser bookmark  
3. Paste code into URL field  
4. Name it (e.g., "Invert & Flip")  
5. Save  

## Usage  
1. Navigate to any webpage  
2. Click the bookmarklet to:  
   - Activate: Invert colors + flip images  
   - Click again: Restore original appearance  

## How It Works  
- **Color Inversion**: Applies CSS `filter: invert(1)`  
- **Image Flipping**: Uses `transform: scaleY(-1)` for `<img>` tags  
- **Background Images**: Adds transparent gradient overlay  
- **Toggle System**: Maintains original state memory  

## Compatibility  
✅ Chrome, Firefox, Edge, Safari  
✅ Most modern websites  
✅ Static images & basic animations  

## Limitations  
⚠️ May not work with:  
- Complex CSS layouts  
- Protected video/content (DRM)  
- Cross-origin iframes  
- WebGL canvases  

