# Multi-Page Profile Application

A clean, accessible web application featuring a profile card, contact form with validation, and a personal reflection page. Built with semantic HTML, CSS, and vanilla JavaScript.

**Live Demo:** https://hng-contactpage.netlify.app

## What's Inside

This project started as a simple profile card and grew into a complete multi-page application. It now includes three main pages that work together to showcase personal information, handle contact requests, and share reflections on the learning journey.

## Pages

### Home Page (index.html)
The landing page displays a profile card with:
- Profile photo and bio
- Real-time timestamp (updates to show current time in milliseconds)
- Social media links (Twitter, GitHub, LinkedIn)
- Lists of hobbies and pet peeves

### Contact Page (contact.html)
A fully functional contact form with:
- Real-time validation as you type
- Clear error messages when something's wrong
- Email format checking
- Message length validation (minimum 10 characters)
- Success confirmation after submission
- All form fields are required

### About Me Page (about.html)
A personal reflection page covering:
- Background and who I am
- What I'm hoping to achieve in this program
- Areas where I'm still building confidence
- A note to my future self
- Additional thoughts and reflections

## Project Structure

```
HNG-CONTACT-PAGES/
├── index.html           # Home page with profile card
├── contact.html         # Contact form
├── about.html          # About me page
├── styles/
│   ├── style.css       # Home page styles
│   ├── navigation.css  # Shared navigation styles
│   ├── contact.css     # Contact page styles
│   └── about.css       # About page styles
├── assets/
│   └── avatar.jpg      # Profile image
└── README.md
```

## Getting Started

### Running Locally

1. Clone or download this repository
```bash
git clone https://github.com/Coderio10/HNG-CONTACT-PAGES.git
cd HNG-CONTACT-PAGES
```

2. Open with a local server (recommended)
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

3. Open your browser to `http://localhost:8000`

Or just double-click `index.html` to open it directly in your browser.

## Features Worth Noting

### Form Validation
The contact form validates everything on the client side:
- Empty fields trigger error messages
- Email must match a valid format (name@domain.com)
- Messages need at least 10 characters
- Errors appear as you leave each field
- Success message shows only after everything checks out

### Accessibility
I tried to make this usable for everyone:
- All form inputs have proper labels
- Error messages are linked to their inputs
- Navigation works with just a keyboard (try pressing Tab)
- Screen readers can understand the page structure
- Focus states are visible when tabbing through

### Responsive Design
The layout adapts to different screen sizes:
- **Mobile** (< 640px): Everything stacks vertically
- **Tablet** (640px - 1023px): Two-column layout for some sections
- **Desktop** (1024px+): Side-by-side layout with profile on the left

## Testing

### Required Test IDs

All elements that need testing have `data-testid` attributes:

**Contact Page:**
- `test-contact-name` - Name input field
- `test-contact-email` - Email input field
- `test-contact-subject` - Subject input field
- `test-contact-message` - Message textarea
- `test-contact-submit` - Submit button
- `test-contact-error-name` - Name error message
- `test-contact-error-email` - Email error message
- `test-contact-error-subject` - Subject error message
- `test-contact-error-message` - Message error message
- `test-contact-success` - Success message after submission

**About Page:**
- `test-about-page` - Main container
- `test-about-bio` - Bio section
- `test-about-goals` - Goals section
- `test-about-confidence` - Low confidence areas
- `test-about-future-note` - Note to future self
- `test-about-extra` - Extra thoughts

**Home Page:**
- `test-profile-card` - Profile card container
- `test-user-name` - User name
- `test-user-bio` - Biography
- `test-user-time` - Timestamp
- `test-user-avatar` - Avatar image
- `test-user-social-links` - Social links container
- `test-user-social-twitter` - Twitter link
- `test-user-social-github` - GitHub link
- `test-user-social-linkedin` - LinkedIn link
- `test-user-hobbies` - Hobbies list
- `test-user-dislikes` - Dislikes list

### Manual Testing

Try these things to see if everything works:
1. Fill out the contact form with invalid data (watch for errors)
2. Submit with valid data (success message should appear)
3. Tab through all pages with your keyboard
4. Resize your browser window (layout should adapt smoothly)
5. Check all three navigation links

## How It Works

### Timestamp
The timestamp on the home page uses `Date.now()` which returns the current time in milliseconds since January 1, 1970. It updates when you load the page.

### Form Validation
The contact form uses JavaScript to check inputs as you interact with them. When you leave a field (blur event), it validates. When you start typing again, errors clear. On submit, everything gets checked one more time.

### Navigation
A sticky navigation bar appears on all pages. The current page gets highlighted so you always know where you are.

## Technologies Used

- **HTML5** - Semantic structure
- **CSS3** - Styling and layout (Flexbox, Grid)
- **JavaScript** - Form validation and interactivity
- **Google Fonts** - Be Vietnam Pro and Open Sans

## Browser Support

Tested and working on:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## What I Learned

Building this taught me a lot about:
- Writing validation that actually helps users (not just blocks them)
- Making forms accessible for screen readers
- Using semantic HTML properly
- Building layouts that work on any screen size
- The importance of giving users clear feedback

## Deployment

This project is deployed on Netlify. Deploying your own is straightforward:

1. Push your code to GitHub
2. Go to Netlify and connect your repository
3. Click deploy (no build configuration needed)

Or use the Netlify CLI:
```bash
netlify deploy --prod
```

## Known Issues

- Form submissions don't actually send anywhere (client-side only)
- Timestamp doesn't auto-update (only on page load)
- No loading states during form submission

These could be good additions in the future.

## Future Improvements

Things I'd like to add:
- Backend to actually handle form submissions
- Email notifications when someone contacts me
- Form data persistence (so you don't lose everything if you refresh)
- Character counter on the message field
- Better animations and transitions

## Author

Kayode Anointed
- GitHub: [@Coderio10](https://github.com/Coderio10)
- Twitter: [@anointedkayode](https://twitter.com/anointedkayode)
- Live Demo: [hng-contactpage.netlify.app](https://hng-contactpage.netlify.app)

## Acknowledgments

Built as part of the HNG Internship program. Thanks to the HNG team for the opportunity to learn and build real projects.

## License

This project is open source and available for educational purposes. Feel free to use it as a reference or starting point for your own projects.