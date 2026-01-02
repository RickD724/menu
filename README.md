# F&I Product Menu - Porsche San Francisco

A clean, modern web application for managing and sharing Finance & Insurance product offerings with customers.

## Features

### Admin Mode
- **Configure Pricing**: Adjust monthly and total prices for all 8 protection plans
- **Generate Customer Links**: Create unique URLs with encoded pricing that can be shared via email
- **Print Menu**: Print-friendly version for deal jackets

### Customer View
- **Product Selection**: Browse and select from 8 different protection plans
- **Real-time Summary**: See selected items and totals update dynamically
- **Submit Selection**: Share selections back with sales representative
- **Mobile Responsive**: Works seamlessly on desktop, tablet, and mobile devices

## Products Included

1. **Porsche Multi-Coverage** - Platinum protection package
2. **Porsche Lease-End Protection** - VSP coverage
3. **Porsche Term Coverage Plus** - Extended protection with rotors
4. **XPEL Surface Protection** - Paint and surface protection
5. **Surface Protection** - Cilajet Ultimate Protection
6. **Porsche Vehicle Service Protection** - 10yr/100K mile coverage
7. **Porsche Dent Protection** - Ding and dent repair
8. **Porsche Premier Tire & Wheel Protection** - Road hazard coverage

## Deployment to Vercel

### Option 1: Quick Deploy (Recommended)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Deploy the file**:
   ```bash
   cd /path/to/fi-menu
   vercel
   ```

3. **Follow the prompts**:
   - Login to your Vercel account
   - Set up project settings (accept defaults)
   - Your site will be live in seconds!

### Option 2: Deploy via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New Project"
3. Import from Git or drag and drop the `fi-menu.html` file
4. Deploy!

### Option 3: GitHub Integration

1. Create a new GitHub repository
2. Push the `fi-menu.html` file
3. Connect the repository to Vercel
4. Automatic deployments on every commit

## Usage Workflow

### For Sales Representatives:

1. **Open Admin Mode** (default view)
2. **Adjust Pricing** for customer-specific deals if needed
3. **Click "Generate Customer Link"**
4. **Copy the generated URL** and email it to your customer
5. Customer receives link and can view/select products
6. Customer submits selection, which you receive

### For Customers:

1. **Open the link** sent by sales representative
2. **Browse products** - scroll through all protection plans
3. **Select desired products** by clicking checkboxes
4. **Review summary** panel on the right (shows totals)
5. **Click "Submit Selection"** to share choices with sales rep
6. **Print summary** for your records if desired

## Technical Details

- **Framework**: Pure HTML/CSS/JavaScript (no dependencies)
- **Styling**: Custom CSS with Porsche brand colors
- **Fonts**: Google Fonts (Cormorant Garamond + DM Sans)
- **Pricing Storage**: Base64 encoded in URL parameters
- **Browser Support**: All modern browsers (Chrome, Firefox, Safari, Edge)
- **Mobile**: Fully responsive design
- **Print**: Optimized print stylesheet included

## Customization

### Changing Colors
Edit CSS variables in the `:root` selector:
```css
:root {
    --porsche-black: #000000;
    --porsche-gold: #C6A972;
    --porsche-red: #D5001C;
    /* etc. */
}
```

### Adding/Removing Products
Edit the `products` array in the JavaScript section:
```javascript
const products = [
    {
        id: 'uniqueId',
        title: 'Product Name',
        subtitle: 'Subtitle',
        icon: '🛡️',
        coverage: 'Coverage details',
        features: ['Feature 1', 'Feature 2']
    },
    // Add more products...
];
```

### Modifying Email Integration
The `submitSelection()` function can be connected to your backend:
```javascript
function submitSelection() {
    // Send to your API endpoint
    fetch('/api/submissions', {
        method: 'POST',
        body: JSON.stringify(selectionData)
    });
}
```

## Security Notes

- Pricing is encoded but **not encrypted** in URLs
- For production, consider implementing:
  - Backend API for pricing storage
  - Authentication for admin mode
  - Database to track customer selections
  - Email integration for automatic notifications

## Browser Requirements

- Modern browser with JavaScript enabled
- Cookies/localStorage not required
- Works offline once page is loaded

## Print Settings

For best print results:
- Use Chrome or Firefox
- Select "Save as PDF" as printer
- Enable background graphics
- Use portrait orientation

## Support

For questions or customization requests, contact your development team.

---

**Version**: 1.0  
**Last Updated**: January 2026  
**License**: Proprietary
