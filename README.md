# Quarto Progress Bar

## Overview

The Quarto Progress Bar is a Lua script designed to display the reading progress of a document as a progress bar in HTML format. This plugin extracts metadata about the total number of pages and the current page number to dynamically generate and display a progress bar within your Quarto document.

## Features

- Automatically displays a progress bar indicating the reading progress.
- Uses document metadata to determine the total number of pages and the current page.
- Displays a textual representation of the progress below the progress bar.

## Prerequisites

- [Quarto](https://quarto.org) installed and set up in your environment.
- Basic understanding of how to use Quarto with Lua filters.

## Installation

Quarto Progress Bar is distributed on GitHub which means you can install it directly into your project by running:

```shell
quarto add errbufferoverfl/quarto-progress-bar
```

By default, the extension will be installed from the `HEAD` of the `main` branch, however, you can target tags and/or branches by including an @ after the repository name.

```shell
quarto add errbufferoverfl/quarto-progress-bar@v1.0
```

## Usage

To use the progress plugin, you need to define the `pages` and `page` metadata in your Quarto document. Here is an example of how to include this metadata at the top of your document:

```qmd
---
title: "Progress Example"
pages: 100
page: 25
---

# Introduction

{{< progress >}}
```

- `pages`: Total number of pages in the document.
- `page`: Current page number.

When you render the document, the plugin will automatically generate a progress bar and display it, indicating the progress through the document.

### Example

Given the above metadata, the progress bar will display as follows:

```html
<progress max="100" value="25"></progress>
<p>Progress: 25/100 pages<p>
```

## Customization

You can customize the appearance of the progress bar by modifying the HTML output in the Lua script. For instance, you can add classes or styles to the `<progress>` and `<p>` elements to better integrate with your site's design.
