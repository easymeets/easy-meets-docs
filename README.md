# easy-meets-docs
This is the github pages implementation of our documentation for easy-meets, 
This readme hosts as a guide to adding and contributing to the documentation when applicable. 

# Adding Pages to MkDocs

1. **Create a new Markdown file**: In your MkDocs project, create a new Markdown file in the `docs` directory. This file will represent your new page. For example, you might create a file called `new_page.md`.

2. **Write your content**: Open the new Markdown file and write your content. You can use any standard Markdown syntax.

3. **Update the navigation**: To make your new page accessible, you need to add it to the navigation structure. This is done in the `mkdocs.yml` file, which is located in the root of your project. Open this file and look for the `nav` or `pages` section (depending on your MkDocs version). Add a new entry for your page. For example:

```yaml
nav:
  - 'Home': 'index.md'
  - 'New Page': 'new_page.md'
```

4. **Preview your site**: Run the `mkdocs serve` command to serve your site locally. When you navigate to your new page, you should see your content.