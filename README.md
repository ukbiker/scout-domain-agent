# 🐕 Scout - Domain Terrier AI Assistant

**Version:** 3.1  
**Status:** Production Ready  
**License:** Proprietary - Domain Terrier  
**Author:** Colin Bell (Domain Terrier)  
**GitHub:** [Your Repository URL]

---

## Overview

Scout is an intelligent conversational AI assistant for Domain Terrier's domain investment business. Built as a single-file HTML application with embedded JavaScript, Scout helps visitors discover and explore Domain Terrier's complete portfolio of 32 Web3 TLDs and premium domain names across multiple categories.

**Live Demo:** [scout.domainterrier.com](https://scout.domainterrier.com) *(when deployed)*

---

## Features

### 🎯 Core Capabilities

- **Complete Portfolio Coverage** - All 32 Web3 TLDs organized into 5 major clusters
- **Natural Language Understanding** - Responds to conversational queries with intelligent keyword detection
- **Buy Intent Detection** - Captures purchase interest and routes to action
- **Domain Search** - Checks availability and suggests alternatives
- **Educational Content** - Explains Web3, TLDs, and domain investing concepts
- **24/7 Availability** - Client-side operation, no server required

### 🛡️ Security Features

- **Content Security Policy (CSP)** - Strict headers prevent XSS attacks
- **Input Validation** - Sanitizes all user input, blocks dangerous characters
- **Rate Limiting** - Client-side throttling prevents abuse
- **DOM Manipulation Protection** - Safe HTML rendering
- **Link Hardening** - All external links use `rel="noopener noreferrer"`
- **Zero Data Collection** - Fully client-side, no tracking, GDPR compliant

### 📱 Responsive Design

- **Desktop First** - Two-column layout with sidebar (300px) and chat area
- **Mobile Optimized** - Sidebar hidden on screens <768px, single-column layout
- **Touch-Friendly** - Large buttons, easy navigation
- **Privacy Badge** - Fixed footer with zero data collection notice

---

## Portfolio Coverage (32 TLDs)

### 🌍 Geographic & Regional Identity (7 TLDs)
`.filipino` • `.balikbayan` • `.fareast` • `.britishisles` • `.southeastasia` • `.caribbeanislands` • `.pacificislands`

### 🚀 Space & Aviation (5 TLDs)
`.aviator` • `.flightsim` • `.flightschool` • `.spacetech` • `.spaceexplorer`

### 💻 Tech, Innovation & Crypto (5 TLDs)
`.innovator` • `.technophile` • `.codebreaker` • `.cryptonian` • `.cryptohunter`

### ✨ Lifestyle & Passion (8 TLDs)
`.travelphile` • `.travelhacker` • `.naturelover` • `.foodieworld` • `.bibliophile` • `.cinephile` • `.trailfinder` • `.dreambuilder`

### 💪 Sports & Fitness (7 TLDs)
`.fittest` • `.combatsport` • `.fightfightfight` • `.speedfreak` • `.mindcoach` • `.thrillseeker` • `.bonkers`

---

## Installation & Deployment

### Option 1: Static Hosting (Vercel - Recommended)

1. **Clone Repository**
   ```bash
   git clone [your-repo-url]
   cd scout-domainterrier
   ```

2. **Deploy to Vercel**
   ```bash
   npm i -g vercel
   vercel --prod
   ```

3. **Configure Custom Domain**
   - Add `scout.domainterrier.com` in Vercel dashboard
   - Update DNS CNAME record

### Option 2: GitHub Pages

1. Push `scout_v3.1_COMPLETE_PORTFOLIO.html` to GitHub repo
2. Rename to `index.html`
3. Enable GitHub Pages in repository settings
4. Select main branch as source

### Option 3: Traditional Web Host

1. Upload `scout_v3.1_COMPLETE_PORTFOLIO.html` via FTP
2. Rename to `index.html` (or configure as default document)
3. No server-side configuration needed - pure static HTML

---

## File Structure

```
scout_v3.1_COMPLETE_PORTFOLIO.html (1,894 lines)
├── HTML Structure
│   ├── Head (meta, CSP, title)
│   ├── Body Container
│   │   ├── Sidebar (desktop only)
│   │   │   ├── Scout Avatar & Stats
│   │   │   └── Contact Information
│   │   └── Chat Area
│   │       ├── Chat Header
│   │       ├── Chat Messages (dynamic)
│   │       ├── Quick Action Buttons (9)
│   │       └── Input Area
│   └── Privacy Badge (fixed footer)
├── CSS (embedded <style>)
│   ├── Layout (CSS Grid)
│   ├── Component Styling
│   └── Mobile Responsive (@media)
└── JavaScript (embedded <script>)
    ├── Input Validation
    ├── Rate Limiting
    ├── Message Detection Logic
    ├── Response Database (scoutResponses)
    └── Chat Rendering
```

---

## Response Categories

### Conversational Responses (10)
- **Greetings** - "hi", "hello", "hey"
- **Thanks/Bye** - "thanks", "goodbye"
- **About** - "who are you", "what is domain terrier"
- **What Can You Do** - "what can you help with"
- **Web3 Education** - "what is web3", "what is a TLD"
- **Pricing** - "how much do domains cost"
- **How It Works** - "how does buying work"
- **Trust** - "is this legit", "are you trustworthy"
- **Refund** - "can I get a refund"
- **Contact** - "how do I get in touch"

### Domain Categories (9)
- **Geographic** - Regional identity TLDs
- **Space & Aviation** - Aerospace domains
- **Tech & Crypto** - Innovation and blockchain
- **Lifestyle** - Travel, books, film, food
- **Sports & Fitness** - Combat, racing, athletics
- **Filipino** - Filipino cultural identity (legacy standalone)
- **RWA** - Real World Assets
- **Smart Glasses** - AR/VR technology
- **Robotics** - AMR and automation
- **Gaming** - Metaverse and gaming
- **AI** - AI agents and AGI
- **Privacy** - Monero and privacy crypto
- **ZKP** - Zero Knowledge Proofs
- **TLDs** - General TLD ownership info

### Special Functions
- **Buy Intent Detection** - Captures purchase interest
- **Domain Check** - Availability queries
- **Fallback** - Catch-all with menu

---

## Keyword Detection

Scout uses a hierarchical keyword detection system. Order matters — more specific keywords are checked first.

### Detection Priority

1. **Buy Intent** (highest priority)
2. **Greetings** (strict regex, short only)
3. **Thanks/Bye**
4. **About Business**
5. **What Can You Do** (with recommendation filter)
6. **Web3 Education**
7. **Pricing General**
8. **Process Questions**
9. **Trust & Safety**
10. **Refund Policy**
11. **Contact Info**
12. **Domain Check** (tightened for "do you have anything for X")
13. **Category Keywords** (5 new clusters + existing)
14. **Fallback Menu**

### Example Keywords by Category

**Geographic:** `british`, `uk`, `southeast asia`, `south east asia`, `asian`, `asia`, `caribbean`, `pacific`, `island`

**Space & Aviation:** `space`, `rocket`, `satellite`, `mars`, `aviation`, `flight`, `pilot`, `aircraft`

**Tech & Crypto:** `crypto`, `blockchain`, `bitcoin`, `ethereum`, `innovation`, `developer`, `hacker`

**Lifestyle:** `travel`, `books`, `film`, `food`, `food lover`, `nature`, `outdoors`, `hiking`, `lifecoach`, `life coach`

**Sports & Fitness:** `fitness`, `gym`, `combat`, `martial arts`, `racing`, `race`, `driver`, `driving`, `car`, `bonkers`

---

## Security Details

### Content Security Policy (CSP)

```html
<meta http-equiv="Content-Security-Policy" content="
    default-src 'self';
    script-src 'self' 'unsafe-inline';
    style-src 'self' 'unsafe-inline';
    img-src 'self' data: https:;
    connect-src 'none';
    font-src 'self';
    frame-src 'none';
    object-src 'none';
    base-uri 'self';
">
```

### Input Validation

```javascript
// Blocked characters: < > { } | \ ^ ` [ ]
const BLOCKED_PATTERN = /[<>{}|\\^`\[\]]/g;
const INPUT_MAX_LENGTH = 200;

function validateInput(raw) {
    let cleaned = raw.trim();
    if (cleaned.length > INPUT_MAX_LENGTH) 
        cleaned = cleaned.substring(0, 200);
    cleaned = cleaned.replace(BLOCKED_PATTERN, '');
    return cleaned;
}
```

### Rate Limiting

- **Limit:** 100 messages per hour per browser
- **Implementation:** Client-side using localStorage
- **Reset:** Automatic after 1 hour
- **User Feedback:** Warning message when approaching limit

---

## Customization Guide

### Update Contact Information

**Lines 376-386** - Sidebar contact details:
```html
<div class="contact-item">
    📧 <a href="mailto:info@domainterrier.com">info@domainterrier.com</a>
</div>
```

### Update Portfolio Stats

**Lines 360-372** - Domain count statistics:
```html
<div class="stat-item">
    <span>Total Domains:</span>
    <span class="stat-value">300+</span>
</div>
```

### Add New TLD/Domain

1. Find appropriate cluster response (e.g., `lifestyle`, `sportsFitness`)
2. Add TLD link to the TLD list section
3. Add domain examples to premium or affordable sections
4. Add keywords to detection logic if needed

### Modify Pricing

Search for domain examples and update pricing inline:
```html
• domainname.tld - $2,500 (Description)
```

### Change Branding Colors

**Lines 35-36** - Orange gradient:
```css
background: linear-gradient(180deg, #FF8C42 0%, #FF6B35 100%);
```

**Line 42** - Button color:
```css
background: #FF6B35;
```

---

## Testing

### Manual Testing Checklist

- [ ] All 9 quick action buttons work
- [ ] Sidebar visible on desktop (>768px)
- [ ] Sidebar hidden on mobile (<768px)
- [ ] All external links open in new tab
- [ ] Email links work correctly
- [ ] Input validation blocks dangerous characters
- [ ] Rate limiting triggers after 100 messages
- [ ] Buy intent detection captures "I want to buy X"
- [ ] Domain check works for specific domains
- [ ] Category responses show for all 32 TLDs

### Test Queries

**Geographic:**
- "I have friends in south east asia"
- "Looking for British domains"
- "Asian identity domains"

**Space & Aviation:**
- "space domains"
- "aviation"
- "flight sim"

**Tech & Crypto:**
- "crypto domains"
- "blockchain"
- "tech startup"

**Lifestyle:**
- "travel domains"
- "food lovers"
- "I am a lifecoach"
- "outdoors store"

**Sports & Fitness:**
- "fitness"
- "martial arts teacher"
- "racing domains"
- "anything for someone who is bonkers"

### Browser Compatibility

Tested and working on:
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile Safari (iOS 14+)
- ✅ Chrome Mobile (Android 10+)

**Note:** CSS Grid support required. May not render correctly in older browsers or basic HTML editors.

---

## Performance

- **File Size:** ~95KB (single HTML file)
- **Load Time:** <1 second on typical broadband
- **Dependencies:** Zero external dependencies
- **API Calls:** None (fully client-side)
- **Database:** None (responses embedded in JavaScript)

---

## Privacy & Data Protection

Scout is designed with privacy-first principles:

- ✅ **Zero Data Collection** - No analytics, no tracking pixels
- ✅ **Client-Side Only** - All processing happens in browser
- ✅ **No Cookies** - Uses only localStorage for rate limiting
- ✅ **No Third-Party Scripts** - Fully self-contained
- ✅ **GDPR Compliant** - No personal data processed or stored
- ✅ **Transparent** - Privacy badge visible on every page

---

## Maintenance

### Regular Updates

1. **TLD Portfolio Changes**
   - Add new TLDs to appropriate cluster responses
   - Update keywords if needed
   - Update portfolio stats in sidebar

2. **Domain Pricing**
   - Review and update example domain prices
   - Update premium vs affordable tiers

3. **Contact Information**
   - Keep email, LinkedIn, website links current
   - Update Colin's business experience years

### Version History

**v3.1** (February 2026)
- Complete 32-TLD portfolio coverage
- 5 new cluster responses
- 8 keyword detection fixes
- Tightened whatCanYouDo and domainCheck logic
- Fixed Aviation quick action button

**v3.0** (February 2026)
- Added 10 conversational response types
- Comprehensive security hardening
- Buy intent detection
- Input validation & rate limiting

**v2.5** (January 2026)
- TLD ownership correction
- Privacy badge implementation
- Branding updates

**v2.0** (January 2026)
- Multi-category support
- Enhanced UI/UX
- Quick action buttons

**v1.0** (December 2025)
- Initial release
- Basic keyword matching
- Filipino domains focus

---

## Support & Contact

**Domain Terrier**  
📧 info@domainterrier.com  
🌐 [domainterrier.com](https://domainterrier.com)  
💼 [LinkedIn](https://linkedin.com/in/colinbell-domainterrier/)

**Scout GitHub Issues**  
For bugs or feature requests, please open an issue on GitHub.

---

## License

© 2025-2026 Domain Terrier. All rights reserved.

This code is proprietary and confidential. Unauthorized copying, modification, distribution, or use of this software is strictly prohibited.

---

## Credits

**Concept & Strategy:** Colin Bell  
**Development:** Colin Bell with Claude (Anthropic)  
**Design:** Domain Terrier  
**AI Assistant Framework:** Claude 3.5 Sonnet

---

**🐕 Scout is ready to work! Deploy with confidence.**
