# Blog

A technical blog built with Jekyll and hosted on GitHub Pages.

## About

This blog covers topics including Python, Django, algorithms, data science, and various programming concepts.

## Development

### Prerequisites

- Ruby 3.2 or higher
- Bundler

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/cgopalan/blog.git
   cd blog
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the development server:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser to `http://localhost:4000`

### Building

To build the site:
```bash
bundle exec jekyll build
```

The generated site will be in the `_site` directory.

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the main branch using GitHub Actions.

## Theme

This blog uses the [Minima](https://github.com/jekyll/minima) theme, which is the default Jekyll theme and provides a clean, modern design.

## License

Content is copyrighted. Code examples are available under MIT license unless otherwise specified.
