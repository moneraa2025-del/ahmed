# ☕ Tea House - بيت الشاي

A modern, bilingual (Arabic/English) website for a 24-hour tea house and café located in Al-Kaaban, Qatar.

## 🌐 Features

- **Fully Responsive Design**: Works perfectly on all devices (desktop, tablet, mobile)
- **Bilingual Support**: RTL (Right-to-Left) Arabic with proper text direction
- **24/7 Service**: Showcase round-the-clock availability
- **Complete Menu**: Display all beverages, food items, and prices
- **Customer Reviews**: 4.8/5 stars with testimonials
- **Contact Integration**: Direct phone and WhatsApp links
- **Modern UI**: Beautiful gradient backgrounds and smooth animations
- **Performance Optimized**: Fast loading times and smooth interactions
- **SEO Ready**: Proper meta tags and semantic HTML

## 📁 File Structure

```
ahmed/
├── tea-house.html      # Main HTML file
├── style-tea.css       # CSS stylesheet
├── script-tea.js       # JavaScript functionality
└── README-tea.md       # This file
```

## 🚀 How to Use

### Option 1: View Locally
1. Download or clone the repository
2. Open `tea-house.html` in your web browser
3. No server required!

### Option 2: Deploy Online
1. Upload files to a web hosting service
2. Or use GitHub Pages for free hosting
3. Share the link with customers

### Option 3: Mobile App
- Open in mobile browser
- Use "Add to Home Screen" for app-like experience

## ☕ Menu Categories

1. **الشاي (Tea)**
   - Black Tea
   - Green Tea
   - Mint Tea
   - Ginger Tea

2. **المشروبات الساخنة (Hot Beverages)**
   - Arabic Coffee
   - Cardamom Coffee
   - Nescafé
   - Hot Chocolate

3. **المشروبات الباردة (Cold Beverages)**
   - Fresh Juices
   - Iced Lemon
   - Cold Cocoa
   - Mineral Water

4. **الساندوتشات (Sandwiches)**
   - Cheese Sandwich
   - Meat Sandwich
   - Chicken Sandwich
   - Vegetable Sandwich

5. **الأطباق الرئيسية (Main Dishes)**
   - Omelet Paratha
   - French Fries
   - Baked Beans
   - Bread & Eggs

6. **الحلويات (Sweets & Appetizers)**
   - Pastries
   - Kunafa
   - Cookies
   - Assorted Sweets

## 📞 Contact Information

- **Phone**: +974 77289797
- **WhatsApp**: https://wa.me/97477289797
- **Location**: Shamal Road, Al-Kaaban, Qatar
- **Hours**: Open 24/7

## 🎨 Customization Guide

### Change Restaurant Details

**Edit in `tea-house.html`:**
```html
<!-- Business name -->
<h1 class="text-2xl font-black text-amber-900">بيت الشاي ☕</h1>

<!-- Phone number -->
<a href="tel:+97477289797">77289797</a>

<!-- Address -->
<p>طريق الشمال، مدينة الكعبان، قطر</p>
```

### Update Phone Numbers
Replace `+97477289797` with your actual phone number:
- In all `tel:` links
- In all WhatsApp links
- In contact section

### Modify Menu Items
Edit the menu section in `tea-house.html`:
```html
<div class="bg-white rounded-lg p-6 shadow-md">
    <h3 class="font-bold text-lg text-amber-900 mb-2">Category Name</h3>
    <ul class="text-gray-700 space-y-2 text-sm">
        <li class="flex justify-between">
            <span>Item Name</span>
            <span>X ر.ق</span>
        </li>
    </ul>
</div>
```

### Change Colors
Edit `style-tea.css`:
```css
:root {
    --amber-900: #78350f;  /* Dark color */
    --amber-700: #b45309;  /* Main color */
    --amber-500: #f59e0b;  /* Accent color */
}
```

### Update Images
Replace image URLs in `tea-house.html`:
```html
<img src="YOUR-IMAGE-URL" alt="Description">
```

## 💻 JavaScript Features

Available functions in `window.teaHouse`:
- `copyToClipboard(text)` - Copy text to clipboard
- `openWhatsApp()` - Open WhatsApp chat
- `makePhoneCall()` - Initiate phone call
- `addToCart(name, price)` - Add items to cart
- `getCartItems()` - Get cart contents
- `shareOnSocial(platform, text)` - Share on social media
- `exportOrder()` - Export order details

## 📱 Responsive Breakpoints

- **Desktop**: Full multi-column layout
- **Tablet (768px)**: Adjusted columns and spacing
- **Mobile (480px)**: Single column layout

## 🔗 External Resources

- **Fonts**: Google Fonts (Cairo)
- **Framework**: Tailwind CSS
- **Images**: Unsplash (free stock photos)

## 🎯 Future Enhancements

- [ ] Online ordering system
- [ ] Payment integration
- [ ] Reservation booking
- [ ] Photo gallery
- [ ] Loyalty program
- [ ] Multi-language support (Arabic/English toggle)
- [ ] Mobile app version
- [ ] Social media integration
- [ ] Customer review system
- [ ] Delivery tracking

## 🌍 Browser Compatibility

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 📊 Analytics & SEO

The website includes:
- Proper meta tags for search engines
- Semantic HTML structure
- Mobile-friendly design (responsive)
- Fast loading performance
- Accessible navigation

## 🔐 Security Notes

- All links are secure (https://)
- WhatsApp links use official API
- No sensitive data stored locally (except cart in localStorage)
- Regular security updates recommended

## 📝 License

© 2026 Tea House - Al-Kaaban, Qatar. All Rights Reserved.

---

**Built with ❤️ for authentic Arabian hospitality** ☕

## 📧 Support

For issues or customization needs, contact the developer or visit the repository.

---

**Last Updated**: January 2026
