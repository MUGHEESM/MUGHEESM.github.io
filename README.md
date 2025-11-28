# Muhammad Mughees - Cybersecurity Portfolio

A professional portfolio website with an integrated blogging platform for cybersecurity expert Muhammad Mughees.

## Features

### Portfolio Website
- **Hero Section**: Professional introduction with cybersecurity theme
- **About Section**: Personal background and statistics
- **Services Section**: Six key cybersecurity services offered
- **Skills Section**: Technical expertise categorized by area
- **Contact Section**: Contact form and social media links
- **Responsive Design**: Mobile-friendly navigation and layouts

### Blogging Platform
- **Create Posts**: Easy-to-use interface for adding new blog posts
- **Categories**: Filter posts by topic (Penetration Testing, Malware Analysis, Cloud Security, etc.)
- **Local Storage**: Posts are saved in browser localStorage
- **Read Posts**: Full-screen modal for reading complete articles
- **Delete Posts**: Remove posts you no longer need
- **Sample Content**: Pre-loaded with 3 sample cybersecurity blog posts

## File Structure

```
mughees/
├── index.html      # Main portfolio page
├── blog.html       # Blog listing and management page
├── styles.css      # All styles for both pages
├── script.js       # Portfolio page interactivity
├── blog.js         # Blog functionality and storage
└── README.md       # This file
```

## How to Use

### Viewing the Website
1. Open `index.html` in a web browser to view the portfolio
2. Navigate through sections using the top menu
3. Click "Blog" or "Read My Blog" to access the blogging platform

### Managing Blog Posts

#### Creating a New Post
1. Go to the Blog page (`blog.html`)
2. Click the "New Post" button
3. Fill in the form:
   - **Title**: Your blog post title
   - **Category**: Select from available categories
   - **Excerpt**: Short description (max 150 characters)
   - **Content**: Full blog post content (supports basic HTML)
   - **Image URL**: Optional image for the post
4. Click "Publish Post"

#### Reading Posts
- Click "Read More" on any blog card to view the full post

#### Filtering Posts
- Use the filter buttons at the top to show posts by category

#### Deleting Posts
- Click the trash icon on any blog card to delete it

## Customization

### Personal Information
Edit `index.html` to update:
- Contact details (email, phone, location)
- Social media links
- About section content
- Profile image (replace placeholder URL)
- Statistics (projects, clients, experience)

### Color Scheme
Modify CSS variables in `styles.css`:
```css
:root {
    --primary-color: #00ff88;    /* Main accent color */
    --secondary-color: #0a192f;  /* Dark background */
    --accent-color: #64ffda;     /* Secondary accent */
    /* ... other colors */
}
```

### Services & Skills
Edit the respective sections in `index.html` to add/remove services and skills.

### Sample Blog Posts
Sample posts are defined in `blog.js`. You can modify or remove them by editing the `blogPosts` array initialization.

## Technologies Used

- **HTML5**: Structure and content
- **CSS3**: Styling with custom properties and animations
- **JavaScript**: Interactivity and blog management
- **Font Awesome**: Icons
- **LocalStorage API**: Blog post persistence

## Browser Compatibility

Works on all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

## Tips

1. **Adding HTML in Blog Posts**: You can use basic HTML tags in the content field:
   - `<h3>Heading</h3>`
   - `<p>Paragraph</p>`
   - `<ul><li>List item</li></ul>`
   - `<code>inline code</code>`

2. **Image URLs**: Use direct image links (ending in .jpg, .png, etc.) or placeholder services

3. **Backup Posts**: Blog posts are stored in browser localStorage. Clearing browser data will delete them.

## Future Enhancements

Consider adding:
- Backend integration for permanent storage
- Markdown support for blog posts
- Search functionality
- Comments section
- RSS feed
- Admin authentication

## License

Feel free to customize and use for your personal portfolio.

---

**Created for Muhammad Mughees - Cybersecurity Expert**
