---
title: "GitHub Pages and Jekyll"
thumbnail: undraw_website_5bo8.svg
description: "Create static site with GitHub Pages and Jekyll."
reading_time: "0:22 mins:secs"
tags: 
  - "Web development"
---

## Introduction

For comprehensive information, refer to the [GitHub Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll){:target="_blank"} and [Jekyll's official site](https://jekyllrb.com/){:target="_blank"}. GitHub Pages uses Jekyll as its static site generator. When you push changes to GitHub, it automatically triggers the Jekyll build process, converting your repository content into static HTML files. Jekyll simplifies the creation of static sites by handling repetitive HTML writing for you. It allows you to define layouts once and use variables, so you don’t have to repeat content across multiple pages.

## GitHub Pages & Jekyll

### Who Can Use This?

GitHub Pages is available for public repositories with GitHub Free and for free organization accounts. By default, GitHub Pages uses GitHub Actions for Jekyll builds. You can bypass this with a `.nojekyll` file in the root of your repository.

### About GitHub Pages and Jekyll

Jekyll is a static site generator that integrates seamlessly with GitHub Pages. It transforms Markdown, HTML, and Liquid (a templating language) files into a static site composed solely of HTML. Jekyll is not officially supported on Windows, so you don’t need to set it up locally; GitHub handles the Jekyll build process for you. Note that you won’t see the build output until you push to GitHub. While you can use other static site generators or custom build actions, we’ll focus on Jekyll here.

### Jekyll Configuration

The `_config.yml` file in your project root contains Jekyll’s settings. For details, refer to the [Jekyll Configuration Documentation](https://jekyllrb.com/docs/configuration/){:target="_blank"}. Some settings are not editable when using GitHub Pages’ built-in Jekyll. Additionally, certain folders and files are ignored by Jekyll based on their names (though you can force inclusion if necessary). You don’t need to delve into these details to set up your site.

### Front Matter

Add YAML Front Matter to the top of your Markdown or HTML files to include metadata like `page.title`. For more information, see the [Jekyll Front Matter Documentation](https://jekyllrb.com/docs/front-matter/){:target="_blank"}. When using GitHub Pages with Jekyll, you also have access to the `site.github` property. For details, refer to the [Jekyll Metadata Documentation](https://jekyll.github.io/github-metadata/site.github/){:target="_blank"}.

### Theme

GitHub offers several supported themes, but we won’t be using them here. For more information, you can explore the available themes on GitHub.

### Plugins

GitHub’s Jekyll setup includes some built-in plugins, and you can add additional ones if needed. However, we won’t cover plugins in this guide.

## Creating a Repository for Your Site

### Create a Repository

Name your repository using all lowercase letters and kebab-case (e.g., `my-repo`). You can create a user or organization site with names like `<user>.github.io` or `<organization>.github.io`, but you can also choose any other name. Make sure to set the repository to public, as private repositories are not available with the free plan.

You can configure GitHub Pages to use a different branch or directory for your site’s source files. If you want to change these settings, refer to [Configuring a Publishing Source for Your GitHub Pages Site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site){:target="_blank"}.

Update the `_config.yml` file as follows:

```yaml
# If you want to force HTTPS, specify the domain without the http at the start, e.g., example.com
domain: "cliffordwilliam.github.io"

# The base hostname and protocol for your site, e.g., http://example.com
url: "https://cliffordwilliam.github.io"

# Specify the folder name if the site is served in a subfolder
baseurl: "/my_archive"
```

Since we are not using a user or organization repository, you need to declare the `baseurl`. Use this variable when declaring hyperlinks later as if not the pages by default will link to '`url/about` and not `url/baseurl/about`.

Commit and push your changes. To publish your site, go to the repository URL > Settings > Pages. Set the main branch as the publishing source and save the changes.

If the build fails and you encounter an indefinite queue, you can try:

```bash
git commit --amend --no-edit
git push --force-with-lease
```

This creates a new commit (even if unchanged) and force pushes it, replacing the old commit.

## Adding Content

Jekyll has two main types of content, **pages** and **posts**.

Pages URLs are `YOUR-SITE-URL/about` or `url/baseurl/about` if you use named repo not user or organization. Refer to [pages](https://jekyllrb.com/docs/pages/){:target="_blank"} in Jekyll. Create pages in root dir. You can use explicit URL for pages if you do not want it to follow how you organize it (you can organize the pages with folders.) in root with permalink but we do not use that in this project.

By default if you use user or organization repo it will look like the ones below, other wise there is the baseurl first before the page resource `url/baseurl/about`.

```bash
.
├── about.md      # => http://example.com/about.html
├── index.html    # => http://example.com/
└── contact.html  # => http://example.com/contact.html
```

Posts are blog posts. Write them in as Markdown (HTML also can) in `_posts`. Refer to [posts](https://jekyllrb.com/docs/posts/){:target="_blank"} in Jekyll. Follow this naming convention, this is opinionated:

```bash
YEAR-MONTH-DAY-title.MARKUP

2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

The content of the Markdown should **start with Front Matter**. Refer to [Front Matter](https://jekyllrb.com/docs/front-matter/){:target="_blank"} in Jekyll. It is YAML within triple-dashed lines. Inside you can declare custom variables for the Markdown post. There are predefined ones too. You use Liquid tags to access these variables in layout when you want to render them. Just like in other templating languages. Front Matter is optional but leave the triple-dashes there, it tells Jekyll to process the file and good for CSS and RSS feeds.

The URL for posts by default are in `url/year/month/day/title.html` or `url/baseurl/year/month/day/title.html`. Use permalink to modify it.

Here are the predefined properties of a Markdown:

- **`layout`**: Write the file name without the extension, the ones in `_layouts` dir. Set to `null` will result in no layout unless you had Front Matter defaults in your `_config.yml` (3.5.0 version lower). Using `none` in a page will cause it to use a layout with the name "none"
- **`permalink`**: Define the explicit URL to overwrite the `url/year/month/day/title.html` or `url/baseurl/year/month/day/title.html`
- **`published`**: Set to false if you do not want this to be generated in build (there is a draft feature but we will not cover that here)

Here are predefined for posts only:

- **`date`**: Set this to overwrite the file name date `YYYY-MM-DD HH:MM:SS +/-TTTT`, hours, minutes, seconds, and timezone offset are optional.
- **`category` `categories`**: This is like placing them in folders, but here you set it explicitly. Specified as a YAML list or a space-separated string. Alters URL path.
- **`tags`**: Same like the above but does not alter their URL.

You create your own layout in `_layouts`, write them in HTML.

```html
---
food: Pizza
---

<h1>{{ page.food }}</h1>
```

Here is an example to how you use the Front Matter in Liquid.

Had to edit the css that i got here to add padding else wont work even if you link another css after this one

post that tried the right way
https://talk.jekyllrb.com/t/rouge-code-snippet-highlighting-not-working/121

post that tried the right way
https://talk.jekyllrb.com/t/canonical-way-to-use-syntax-highlighting-of-code-blocks/4645

link for css for highlight
https://frankindev.com/2017/03/18/syntax-highlight-with-rouge-in-jekyll/

## Important Considerations

- **Availability**: GitHub Pages is accessible for public repositories with GitHub Free, including the free tier for organizations.
- **Bypassing Jekyll**: To bypass the Jekyll build process, place a `.nojekyll` file in the root of your repository.
- **Windows Support**: Jekyll is not officially supported on Windows, so you don’t need to set it up locally if using GitHub Pages.
- **Restrictions**: Organization owners can restrict GitHub Pages publications.
- **Configuration Limitations**: Some settings cannot be modified when using GitHub Pages’ default Jekyll setup.
- **Ignored Files**: Jekyll ignores certain folders and files based on their names, though you can force their inclusion if necessary.
- **Metadata**: When using GitHub with Jekyll, the `site.github` property provides access to your repository’s metadata.
- **Themes**: Only certain themes are supported with GitHub Pages’ Jekyll integration.
- **Plugins**: GitHub Pages’ Jekyll setup includes some built-in plugins.
- **Repository Naming**: Name your repository using lowercase letters and kebab-case (e.g., `<user>.github.io` or `<organization>.github.io`). You can also use other names for personal repositories.
- **Build Failures**: If the build fails and reports an invalid token (even if you haven't used one), amend your commit and force push to trigger a new build queue.
