Proxy Mirrors Catalog
=====================

A modern, responsive web interface for showcasing and managing proxy mirrors for various package managers and Linux distributions. This project provides a clean, interactive dashboard that allows users to easily discover and configure proxy mirrors for development tools and operating systems.

Live on:https://nexus.son.ir/mirrors

 Features
----------

###  Modern UI/UX

*   **Dark/Light Theme Support** - Toggle between themes with persistent user preference
    
*   **Responsive Design** - Fully responsive layout that works on mobile, tablet, and desktop
    
*   **Interactive Cards** - Hover effects, animations, and active states for better user experience
    
*   **Real-time Search** - Filter mirrors by name as you type
    

###  Mirror Management

*   **Comprehensive Mirror Categories**:
    
    *   **Development Mirrors**: Composer, Maven, NPM, NuGet, PyPI, Docker
        
    *   **Linux Distribution Mirrors**: Alpine Linux, Rocky Linux, Ubuntu
        
*   **Detailed Configuration Guides** - Step-by-step setup instructions for each mirror
    
*   **One-Click Copy** - Copy configuration snippets with a single click
    
*   **Visual Feedback** - Toast notifications for successful copy actions
    

### 💻 Technical Features

*   **Client-side Rendering** - No server-side dependencies required
    
*   **Local Storage** - Theme preferences saved locally
    
*   **Accessibility** - Semantic HTML and ARIA labels
    
*   **Performance Optimized** - Minimal dependencies, fast loading
    

 Quick Start
--------------

### Prerequisites

*   A web server (Apache, Nginx, or any static file server)
    
*   Modern web browser with JavaScript enabled
    

### Installation

1.  Clone the repository:
    

```bash
git clone https://github.com/Ansarisepehr/proxy-mirrors.git
cd proxy-mirrors-catalog
```

2.  Deploy the files to your web server:
    

```bash
# For Apache
sudo cp -r . /var/www/html/mirrors/

# For Nginx
sudo cp -r . /usr/share/nginx/html/mirrors/
```

3.  Ensure proper file permissions:

```bash
sudo chmod -R 755 /path/to/mirrors/   `
```

4.  Configure your web server to serve the index.html file
    

 Project Structure
---------------------

```text
proxy-mirrors/
│
├── index.html              # Main HTML file
├── README.md               # This documentation
├── docs/                    # Deployment Structures
│   └── DEPLOYMENT.md
│
├── conf/                    # Nginx Configuration file
│   └── nginx.conf
│
├── svg/                    # SVG logo assets
│   ├── composer-logo.svg
│   ├── maven-logo.svg
│   ├── npm-logo.svg
│   ├── nuget-logo.svg
│   ├── pypi-logo.svg
│   ├── docker-logo.svg
│   ├── alpine-logo.svg
│   ├── rocky-logo.svg
│   ├── ubuntu-logo.svg
│   ├── github-logo.svg
│   ├── telegram-logo.svg
│   ├── gmail-logo.svg
│   └── linkedin-logo.svg
│
├── png/                    # PNG image assets
│   ├── sepehr-infinity.png
│   └── developer-avatar.png
│
└── gif/                    # Animated GIF assets
    └── bat.gif
```

 Configuration
----------------

### Customizing Mirrors

Edit the mirrors object in the JavaScript section of index.html to add or modify mirror configurations:

```javascript
const mirrors = {
    your_mirror_name: {
        title: "Your Mirror Title",
        url: "https://your-domain.com/repository/path/",
        logo: "svg/logo-name.svg",
        description: `Your configuration instructions here...`
    }
    // Add more mirrors as needed
};
```
### Adding New Categories

To add a new category section:

1.  Add a new section in the HTML:
    

```html
   <section id="new-category">
    <h2>New Category Name</h2>
    <div class="cards-row">
        <!-- Add cards here -->
    </div>
</section>    
```

2.  Add corresponding mirror definitions in the JavaScript mirrors object
    

### Customizing Styling

The application uses CSS custom properties for theming. Modify the color scheme in the :root and \[data-theme="light"\] selectors:

```css
:root {
    --bg: #0d1117;
    --card-bg: #161b22;
    --accent: #ff9f1c;
    /* Add more custom properties */
}
```

 Supported Mirrors
--------------------

### Development Package Managers

Mirror	Description	Configuration Type
Composer	PHP package manager	composer.json
Maven	Java build tool	settings.xml / pom.xml
NPM	Node.js package manager	npm config
NuGet	.NET package manager	dotnet CLI
PyPI	Python package index	pip.conf
Docker	Container registry	daemon.json

### Linux Distributions

DistributionVersionsPackage Manager**Alpine Linux**Various branchesapk**Rocky Linux**BaseOS, AppStream, EPEL, Extrasdnf/yum**Ubuntu**24.04 (Noble)apt

📱 Browser Support
------------------

*   Chrome 60+
    
*   Firefox 55+
    
*   Safari 11+
    
*   Edge 79+
    
*   Opera 47+
    

 Development
--------------

### Local Development

1.  Open index.html directly in a browser for local testing
    
2.  Use Live Server extension in VS Code for hot reload
    
3.  Test with different screen sizes using browser dev tools
    

### Building Custom Assets

*   SVG logos should be optimized for web (use tools like SVGOMG)
    
*   PNG images should be compressed (use tools like TinyPNG)
    
*   Keep file sizes small for better performance
    

 Contributing
---------------

1.  Fork the repository
    
2.  Create a feature branch: git checkout -b feature/amazing-feature
    
3.  Commit your changes: git commit -m 'Add amazing feature'
    
4.  Push to the branch: git push origin feature/amazing-feature
    
5.  Open a Pull Request
    

### Contribution Guidelines

*   Follow existing code style and structure
    
*   Add comments for complex logic
    
*   Update documentation as needed
    
*   Test changes thoroughly


 Acknowledgments
------------------

*   Icons from respective project official logos
    
*   Color scheme inspired by GitHub Dark/Light themes
    
*   Design inspiration from modern dashboard interfaces
    

 Support
----------

For support, questions, or feature requests:

1.  Check the [Issues](https://github.com/AnsariSepehr/proxy-mirrors/issues) page
    
2.  Create a new issue with detailed description
    
3.  For security issues, please disclose responsibly
    

 Related Projects
-------------------

*   [Nexus Repository Manager](https://www.sonatype.com/products/nexus-repository) - Repository manager for proxy configuration
    
*   [Artifactory](https://jfrog.com/artifactory/) - Alternative repository manager
    
*   [Verdaccio](https://verdaccio.org/) - Lightweight private npm proxy registry
    

**Note**: This is a frontend interface for displaying proxy mirror configurations. Actual proxy server setup and configuration must be done separately using appropriate repository management software like Nexus Repository Manager.
