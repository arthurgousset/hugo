# Hugo (Cheat Sheet)

## Install Hugo 

With Homebrew: 

```sh
brew install hugo
```

Source: [gohugo.io](https://gohugo.io/installation/macos/#homebrew)

### Create post

```bash
hugo new posts/<file.md>
```

### Clone Hugo website on new device

Install Hugo: `brew install hugo`.

Clone repo and submodules (e.g. themes):

```bash
git clone --recurse-submodules <repo>
```

Fetch and merge updates in submodule:

```bash
git submodule update --remote
```

_Source: [Git docs - 7.11 Git Tools - Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)_


Build and host locally `hugo server -D`

### Visualise Hugo in VS Code

1. In your terminal type `hugo server -D`
2. Copy the localhost address e.g. `http://localhost:1313/`
3. Open the command pallete (`Ctrl` + `Shift` + `P`)
4. Select "Simple Browser: Show"
5. Enter URL/web address (e.g. `http://localhost:1313/`)
6. Press `Enter`

Source: [Stack Overflow](https://stackoverflow.com/a/68539272)

### Exclude some files

In `config.yml`, to exclude specific files from the `content` and `data` directories when rendering your site, set `ignoreFiles` to one or more regular expressions to match against the absolute file path.

To ignore files ending with `.foo` or `.boo`:

```yaml
ignoreFiles:
- \.foo$
- \.boo$
```

To ignore a file using the absolute file path:

```yaml
ignoreFiles:
- ^/home/user/project/content/test\.md$
```


Source: [gohugo.io  - Ignore Content and Data Files when Rendering](https://gohugo.io/getting-started/configuration/#ignore-content-and-data-files-when-rendering)

### Modify syntax highlighting

Instructions copied from [PaperMod/FAQs/Using Hugo’s Syntax highlighter “chroma”](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-faq/#using-hugos-syntax-highlighter-chroma).

1. Disable Highlight.js in site `config.yml`

    ```yml
    params:
        assets:
            disableHLJS: true
    ```

2. Set hugo's markdown styling in site `config.yml`

    Find styles here: [Chrome Style Gallery](https://xyproto.github.io/splash/docs/all.html)

    ```yml
    markup:
        highlight:
            # anchorLineNos: true
            codeFences: true
            guessSyntax: true
            lineNos: true
            # noClasses: false
            style: monokai
    ```

3. If you want `lineNos: true`, the background won't be proper.
   This will only work with `noClasses: false` or `pygmentsUseClasses: true`.
   Read [Generate Syntax Highlighter CSS](https://gohugo.io/content-management/syntax-highlighting/#generate-syntax-highlighter-css)

    Add the following to `assets/css/extended/custom.css`

    ```css
    .chroma {
        background-color: unset;
    }
    ```

    More Info : [Configure Markup - Highlight](https://gohugo.io/getting-started/configuration-markup#highlight)

"Official" config from [Hugo docs](https://gohugo.io/getting-started/configuration-markup#highlight) (for comparison):

```yaml
markup:
  highlight:
    anchorLineNos: false
    codeFences: true
    guessSyntax: false
    hl_Lines: ""
    lineAnchors: ""
    lineNoStart: 1
    lineNos: false
    lineNumbersInTable: true
    noClasses: true
    noHl: false
    style: monokai
    tabWidth: 4
```

## Social icons

See here: [github.com/adityatelange/hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod/wiki/Icons)
