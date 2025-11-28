# How to Add New Blog Posts

Your blog now uses a **JSON file system** that makes it easy to add, edit, and manage posts!

## 📝 Adding a New Blog Post

### Option 1: Quick Text Post

1. **Open `blog-posts.json`** in your editor
2. **Add a new post object** at the top of the array:

```json
[
    {
        "id": 5,
        "title": "Your New Post Title",
        "category": "walkthrough",
        "excerpt": "Short 150 character description of your post...",
        "content": "<h3>Introduction</h3><p>Your content here with HTML tags...</p>",
        "image": "https://via.placeholder.com/800x400/0a192f/00ff88?text=Your+Post",
        "date": "2025-12-01"
    },
    // ... existing posts below
]
```

3. **Save the file**
4. **Push to GitHub:**
```powershell
git add blog-posts.json
git commit -m "Added new blog post"
git push
```

5. **Done!** Your site updates automatically in 1-2 minutes.

---

### Option 2: Detailed Walkthrough (Like Blue)

1. **Create a new folder:**
   - `Walthroughs/YourBoxName/`

2. **Add your walkthrough HTML file:**
   - `Walthroughs/YourBoxName/walkthrough.html`
   - Copy the structure from Blue walkthrough
   - Add all your images to the same folder

3. **Update `blog-posts.json`:**

```json
{
    "id": 6,
    "title": "Your Box Name Walkthrough",
    "category": "walkthrough",
    "excerpt": "Brief description of the box and vulnerabilities...",
    "content": "<h3>Overview</h3><p>Short intro...</p><p><a href='Walthroughs/YourBoxName/walkthrough.html' style='color: var(--primary-color);'>Read the full walkthrough →</a></p>",
    "image": "https://via.placeholder.com/800x400/0a192f/00ff88?text=Your+Box",
    "date": "2025-12-01",
    "isExternal": true,
    "externalLink": "Walthroughs/YourBoxName/walkthrough.html"
}
```

4. **Push everything:**
```powershell
git add .
git commit -m "Added YourBoxName walkthrough"
git push
```

---

## 📋 Available Categories

- `walkthrough` - CTF/machine walkthroughs
- `penetration-testing` - Pentest techniques
- `malware` - Malware analysis
- `cloud-security` - Cloud security topics
- `best-practices` - Security best practices
- `news` - Security news/updates

---

## 🎨 Post Fields Explained

| Field | Required | Description |
|-------|----------|-------------|
| `id` | ✅ Yes | Unique number (use timestamp or increment) |
| `title` | ✅ Yes | Post title (shown on cards) |
| `category` | ✅ Yes | One of the categories above |
| `excerpt` | ✅ Yes | Short description (max 150 chars) |
| `content` | ✅ Yes | Full HTML content (use `<h3>`, `<p>`, `<ul>`, etc.) |
| `date` | ✅ Yes | Format: YYYY-MM-DD |
| `image` | ❌ No | Thumbnail image URL |
| `isExternal` | ❌ No | Set to `true` for walkthrough pages |
| `externalLink` | ❌ No | Path to detailed walkthrough HTML |

---

## 💡 Tips

1. **Always increment the ID** - Use unique numbers for each post
2. **Escape quotes** - Use `'` instead of `"` inside content strings
3. **Test locally** - Open `blog.html` in browser before pushing
4. **Date format** - Always use YYYY-MM-DD format
5. **Images** - Use placeholder URLs or host images in your repo

---

## 🚀 Workflow Summary

```
1. Edit blog-posts.json (add new post)
2. (Optional) Create walkthrough HTML + images
3. git add .
4. git commit -m "Your message"
5. git push
6. Wait 1-2 minutes
7. Your site is updated! 🎉
```

---

## ❓ Need Help?

- **JSON validator:** https://jsonlint.com/ (check for errors)
- **HTML entities:** Escape special characters in content
- **Image hosting:** Use GitHub repo or external services

---

## 🔧 Advanced: Removing the "New Post" Button

Since posts are now managed via JSON, you may want to hide the "New Post" button on the live site.

In `blog.html`, find and remove (or comment out) this line:
```html
<button id="newPostBtn" class="btn btn-primary"><i class="fas fa-plus"></i> New Post</button>
```

This prevents confusion since the button won't save posts permanently anymore.
