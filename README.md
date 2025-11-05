# Omar Riestra - Personal Website & Portfolio

**URL**: https://omarriestra.github.io/

A modern, responsive website built with **Hugo** and the **Congo** theme, showcasing my work in technology, automation, and artificial intelligence.

## 🏗️ Architecture

- **Static Site Generator**: Hugo v0.152.2 (Extended)
- **Theme**: Congo (Tailwind CSS 3.0 based)
- **Hosting**: GitHub Pages
- **Deployment**: Manual (Git-based)

## 📁 Project Structure

```
omarriestra.github.io/
├── content/                    # Main content directory
│   ├── about.md               # About page
│   ├── posts/                  # Blog posts
│   │   └── _index.md          # Blog section landing
│   ├── projects/              # Projects showcase
│   │   └── _index.md          # Projects section landing
│   └── ai-briefings/          # AI Intelligence Briefings
│       └── _index.md          # AI Briefings section landing
├── assets/                    # Static assets
│   └── img/                   # Images
├── data/                      # Data files
│   └── writing-profile.toml   # Personal writing style configuration
├── themes/                    # Hugo themes
│   └── congo/                 # Congo theme (Git submodule)
├── static/                    # Static files
├── hugo.toml                  # Hugo configuration
└── README.md                  # This file
```

## 🚀 Getting Started

### Prerequisites

- **Hugo Extended**: Install using `winget install Hugo.Hugo.Extended`
- **Git**: For version control
- **Node.js**: (Optional) For additional tooling

### Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/omarriestra/omarriestra.github.io.git
   cd omarriestra.github.io
   ```

2. **Start development server**:
   ```bash
   hugo server --buildDrafts
   ```
   Visit `http://localhost:1313` to preview changes

3. **Build for production**:
   ```bash
   hugo --buildDrafts
   ```

## 📝 Content Creation

### Blog Posts
Create new posts in the `content/posts/` directory:
```bash
hugo new content posts/my-new-post.md
```

### Projects
Add new projects in the `content/projects/` directory:
```bash
hugo new content projects/project-name.md
```

### AI Briefings
Manually curate and add AI briefings in `content/ai-briefings/`:
```bash
hugo new content ai-briefings/briefing-date.md
```

## 🎨 Writing Profile

The site uses a personalized writing profile defined in `data/writing-profile.toml`:

- **Voice**: Conversational, curious, and analytical
- **Language**: Spanish (primary) with English support
- **Tone**: Approachable yet technical
- **Focus**: Practical innovation and continuous learning

### Content Guidelines

1. **Length Guidelines**:
   - Blog posts: 800-1500 words
   - Projects: 300-600 words
   - AI briefings: 1000-2000 words

2. **Structure**:
   - Use clear headings and subheadings
   - Include bullet points for readability
   - Add summary and key takeaways
   - Provide actionable insights

3. **Topics**:
   - Primary: AI, automation, digital transformation
   - Secondary: Travel tech, cloud computing, data analytics

## 📊 Sections Overview

### 🏠 About
Personal introduction, expertise areas, and professional background.

### 🚀 Projects
Showcase of technology projects, automation solutions, and innovation work.

### 📝 Blog
Thoughts on technology, innovation, and digital transformation trends.

### 🤖 AI Briefings
Curated insights on artificial intelligence developments and industry news.

## 🔧 Configuration

### Hugo Configuration (`hugo.toml`)

Key settings:
- **Base URL**: `https://omarriestra.github.io/`
- **Language**: Spanish (`es-es`)
- **Theme**: Congo
- **Appearance**: Dark mode default, auto-switch enabled

### Theme Customization

The Congo theme is customized with:
- Personal brand colors and styling
- Custom navigation menu
- Social media links (GitHub, LinkedIn)
- Analytics ready (disabled by default)

## 📱 Publishing Workflow

### Step 1: Create Content
1. Write content following the writing profile guidelines
2. Add appropriate frontmatter metadata
3. Review for technical accuracy and clarity

### Step 2: Local Preview
```bash
hugo server --buildDrafts
```
Preview at `http://localhost:1313`

### Step 3: Build & Deploy
```bash
# Build the site
hugo --buildDrafts

# Commit and push changes
git add .
git commit -m "Add new content"
git push origin main
```

GitHub Pages will automatically deploy the updated site.

## 📈 Analytics & SEO

### Google Analytics (Optional)
1. Update `hugo.toml` with your Google Analytics ID
2. Set `params.analytics.enable = true`
3. Configure `params.analytics.property = "GA_MEASUREMENT_ID"`

### SEO Best Practices
- Use descriptive page titles and meta descriptions
- Add relevant tags and categories
- Include internal links between related content
- Optimize images for web performance

## 🛠️ Maintenance

### Regular Tasks
- **Weekly**: Review and publish new content
- **Monthly**: Update project showcases and achievements
- **Quarterly**: Review analytics and content performance
- **Annually**: Update skills, expertise, and portfolio

### Updates
- **Hugo**: Check for new versions quarterly
- **Theme**: Update Congo theme as needed
- **Dependencies**: Review and update any additional tools

## 📧 Contact

- **GitHub**: [@omarriestra](https://github.com/omarriestra)
- **LinkedIn**: [Omar Riestra](https://www.linkedin.com/in/omarriestra/)
- **Email**: contact@example.com

## 📄 License

This website and its content are licensed under the MIT License.

---

*Built with ❤️ using Hugo and the Congo theme*