**Zuygui's blog**

> A blog about my projects

![Access to the blog](https://zuygui.github.io/blog)

## Description

This repository contains the source code for my personal blog, which is built using Hugo (GoHugo) - a fast and flexible static site generator - and styled with the Terminal theme. The blog focuses on my code projects . It aims to provide valuable insights, tutorials, and articles to the community.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Installation

To set up the blog locally on your machine, follow these steps:

1. **Clone the repository**:

   ```
   git clone https://github.com/zuygui/blog.git
   ```

2. **Install Hugo**:
   Make sure you have [Hugo](https://gohugo.io/getting-started/installing/) installed on your system.

3. **Navigate to the project folder**:

   ```
   cd blog
   ```

4. **Start the development server**:

   ```
   hugo server -D
   ```

   The development server will be available at `http://localhost:1313/`. You can now view your blog locally in your web browser.

## Usage

The blog is structured as follows:

- one post per project
- tags
- keywords

Feel free to explore and modify the content to suit your preferences and needs.

## Customization

### Theme

The blog is using the Terminal theme, which provides a minimalist and sleek design. You can customize the theme by modifying the relevant files in the `themes/terminal/` directory.

### Configuration

You can update the blog's configuration by editing the `config.toml` file. Adjust the site title, description, social media links, and other settings to personalize your blog.

### Content

To create a new blog post, you can use the following command:

```
hugo new posts/your-post-title.md
```

This will generate a new Markdown file in the `content/posts/` directory. Open the file with your favorite text editor and start writing your blog post using Markdown syntax.

## Contributing

If you find any issues with the blog, such as bugs, typos, or have suggestions for improvements, feel free to open an issue or submit a pull request. Your contributions are greatly appreciated!

## License

The content of this blog is licensed under the MIT Licence. Feel free to use the code and content as a reference or reuse it for your projects. However, please provide appropriate credit to this repository.

---

_Note: Customize this README.md file according to your specific blog features, customizations, and preferences._
