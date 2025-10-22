# Multi-Page Profile Application - Stage 1

A fully accessible, responsive multi-page web application featuring a profile card, contact form, and reflective about page. Built with semantic HTML, CSS, and vanilla JavaScript.

**Live Demo:** https://myprofile-card-hng.netlify.app/

## Project Overview

This is Stage 1 of the HNG Frontend track, building upon the Stage 0 profile card by adding two new pages with form validation, accessibility features, and responsive design.

### Pages Included

1. **Home (index.html)** - Profile card with user information, social links, hobbies, and dislikes
2. **Contact Us (contact.html)** - Form with client-side validation
3. **About Me (about.html)** - Reflective page with personal journey and goals

## Features

### Contact Page
- Real-time form validation
- All fields required with specific rules
- Email format validation
- Message minimum length (10 characters)
- Error messages tied to inputs with `aria-describedby`
- Success confirmation after valid submission
- Fully keyboard accessible
- All labels properly linked with `for` attributes

### About Page
- Five required sections with personal reflections
- Semantic HTML structure with proper landmarks
- Engaging content about journey, goals, and growth
- Responsive card-based layout

### General
- Semantic HTML5 throughout
- WCAG 2.1 accessibility compliant
- Responsive design (mobile, tablet, desktop)
- Navigation between all pages
- All test IDs included for automated testing

## Test IDs Reference

### Contact Page
- `test-contact-name` - Full name input
- `test-contact-email` - Email input
- `test-contact-subject` - Subject input
- `test-contact-message` - Message textarea
- `test-contact-submit` - Submit button
- `test-contact-error-name` - Name error message
- `test-contact-error-email` - Email error message
- `test-contact-error-subject` - Subject error message
- `test-contact-error-message` - Message error message
- `test-contact-success` - Success message

### About Page
- `test-about-page` - Main container
- `test-about-bio` - Biography section
- `test-about-goals` - Goals section
- `test-about-confidence` - Low confidence areas section
- `test-about-future-note` - Note to future self section
- `test-about-extra` - Extra thoughts section

### Home Page (Stage 0)
- `test-profile-card` - Profile card container
- `test-user-name` - User name
- `test-user-bio` - Biography
- `test-user-time` - Timestamp (milliseconds)
- `test-user-avatar` - Avatar image
- `test-user-social-links` - Social links container
- `test-user-social-twitter` - Twitter link
- `test-user-social-github` - GitHub link
- `test-user-social-linkedin` - LinkedIn link
- `test-user-hobbies` - Hobbies list
- `test-user-dislikes` - Dislikes list

## Getting Started

### Prerequisites
- A modern web browser
- Git (optional, for cloning)
- A local server (optional but recommended)

### Installation

1. Clone the repository
```bash
git clone https://github.com/Coderio10/profile-card.git
cd profile-card
```

2. Open with a local server
```bash
# Python
python -m http.server 8000

# Node.js
npx serve .

# PHP
php -S localhost:8000
```

3. Navigate to `http://localhost:8000`

Or simply open `index.html` in your browser.

## Project Structure

```
profile-card/
├── index.html          # Home page with profile card
├── contact.html        # Contact form page
├── about.html          # About me page
├── style.css           # Home page styles
├── contact.css         # Contact page styles
├── about.css           # About page styles
├── assets/
│   ├── avatar.jpg      # Profile image
│   └── [other assets]
└── README.md
```

## Form Validation Rules

The contact form validates the following:

1. **All fields required** - Cannot submit with empty fields
2. **Email format** - Must match pattern: `name@example.com`
3. **Message length** - Minimum 10 characters
4. **Real-time feedback** - Errors show on blur, clear on input
5. **Success state** - Confirmation message displays after valid submission

## Accessibility Features

### Forms
- All inputs have associated `<label>` elements
- Error messages linked with `aria-describedby`
- Required fields marked with `aria-required="true"`
- Invalid fields have `aria-invalid="true"`
- Success/error messages use `role="alert"`
- Live regions with `aria-live="polite"`

### Navigation
- Semantic `<nav>` element with `aria-label`
- Current page indicated with `aria-current="page"`
- Keyboard navigable with visible focus states

### Content
- Proper heading hierarchy (h1, h2, h3)
- Semantic landmarks (main, section, nav, header, footer)
- Alt text for all images
- Screen reader text where needed

## Responsive Breakpoints

- **Mobile**: < 640px - Single column, stacked layout
- **Tablet**: 640px - 1023px - Two column where appropriate
- **Desktop**: 1024px+ - Full layout with side-by-side sections

## Testing the Application

### Manual Testing Checklist

**Contact Form:**
- [ ] All fields show error when empty and submitted
- [ ] Email validates format correctly
- [ ] Message validates minimum 10 characters
- [ ] Success message shows after valid submission
- [ ] Form resets after successful submission
- [ ] Keyboard navigation works (Tab through fields)
- [ ] Error messages are announced by screen readers

**About Page:**
- [ ] All five sections are present with correct data-testids
- [ ] Content is readable and properly formatted
- [ ] Page is responsive on all screen sizes
- [ ] Semantic structure is correct

**Navigation:**
- [ ] Links work between all three pages
- [ ] Active page is visually indicated
- [ ] Navigation is keyboard accessible

### Automated Testing Example

```javascript
// Contact form validation tests
test('shows error for invalid email', async () => {
  const emailInput = screen.getByTestId('test-contact-email');
  const submitBtn = screen.getByTestId('test-contact-submit');
  
  fireEvent.change(emailInput, { target: { value: 'invalid-email' } });
  fireEvent.click(submitBtn);
  
  const errorMsg = screen.getByTestId('test-contact-error-email');
  expect(errorMsg).toHaveTextContent(/valid email/i);
});

test('shows success message on valid submission', async () => {
  // Fill all fields with valid data
  fireEvent.change(screen.getByTestId('test-contact-name'), { 
    target: { value: 'John Doe' } 
  });
  fireEvent.change(screen.getByTestId('test-contact-email'), { 
    target: { value: 'john@example.com' } 
  });
  fireEvent.change(screen.getByTestId('test-contact-subject'), { 
    target: { value: 'Hello' } 
  });
  fireEvent.change(screen.getByTestId('test-contact-message'), { 
    target: { value: 'This is a test message' } 
  });
  
  fireEvent.click(screen.getByTestId('test-contact-submit'));
  
  const successMsg = screen.getByTestId('test-contact-success');
  expect(successMsg).toBeVisible();
});
```

## Deployment

This project is deployed on Netlify. To deploy your own:

1. Push to GitHub
2. Connect repo in Netlify dashboard
3. Deploy (no build configuration needed)

Or use Netlify CLI:
```bash
netlify deploy --prod
```

## Browser Compatibility

Tested and working on:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## What I Learned

Building this stage taught me several important lessons:

1. **Form Validation** - Implementing accessible validation that works for everyone
2. **Error Handling** - Providing clear, helpful error messages
3. **ARIA Attributes** - Using ARIA correctly to enhance accessibility
4. **Semantic Structure** - Building pages with proper HTML landmarks
5. **Multi-page Navigation** - Creating consistent navigation across pages

## Future Improvements

- Add backend form submission
- Implement form data persistence
- Add loading states
- Include form field character counters
- Add animations for better UX

## Author

Kayode Anointed
- GitHub: [@Coderio10](https://github.com/Coderio10)
- Twitter: [@anointedkayode](https://twitter.com/anointedkayode)

## Acknowledgments

- HNG Internship program
- MDN Web Docs for accessibility guidelines
- W3C for form accessibility patterns

## License

This project is open source and available for educational purposes.