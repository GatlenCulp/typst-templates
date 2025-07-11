# International Conference on Learning Representations (ICLR)

## Usage

You can use this template in the Typst web app by clicking _Start from
template_ on the dashboard and searching for `clear-iclr`.

Alternatively, you can use the CLI to kick this project off using the command

```shell
typst init @preview/clear-iclr
```

Typst will create a new directory with all the files needed to get you started.

## Example Papers

Here are an example paper in [LaTeX][1] and in [Typst][2].

## Configuration

This template exports the `iclr` function with the following named arguments.

- `title`: The paper's title as content.
- `authors`: An array of author dictionaries. Each of the author dictionaries
  must have a name key and can have the keys department, organization,
  location, and email.

  ```typst
  #let authors = (
    ...,
    (
      names: ([Coauthor1], [Coauthor2]),
      affilation: [Affiliation],
      address: [Address],
      email: "correspondent@example.org",
    ),
    ...
  )
  ```
- `keywords`: Publication keywords (used in PDF metadata).
- `date`: Creation date (used in PDF metadata).
- `abstract`: The content of a brief summary of the paper or none. Appears at
  the top under the title.
- `bibliography`: The result of a call to the bibliography function or none.
  The function also accepts a single, positional argument for the body of the
  paper.
- `appendix`: Content to append after bibliography section (can be included).
- `accepted`: If this is set to `false` then anonymized ready for submission
  document is produced; `accepted: true` produces camera-redy version. If
  the argument is set to `none` then preprint version is produced (can be
  uploaded to arXiv).
- `aux`: Auxiliary parameters to tune font settings (e.g. font familty) or page
  decorations (e.g. page header).

The template will initialize your package with a sample call to the `iclr`
function in a show rule. If you want to change an existing project to use this
template, you can add a show rule at the top of your file.

## Issues

- Common issue is related to Typst's inablity to produce colored annotation. In
  order to mitigte the issue, we add a script which modifies annotations and
  make them colored.

  ```shell
  ../colorize-annotations.py \
      example-paper.typst.pdf example-paper-colored.typst.pdf
  ```

  See [README.md][3] for details.

- The author instructions says that preferable font is MS Times New Roman but
  the official example paper uses serifs like Computer Modern and Nimbus font
  families. Monospace fonts are not specified.

- ICML-like bibliography style. The bibliography slightly differs from the one
  in the original example paper. The main difference is that we prefer to use
  author's lastname at first place to search an entry faster.

[1]: example-paper.latex.pdf
[2]: example-paper.typst.pdf
[3]: ../#colored-annotations
[2024]: https://iclr.cc/Conferences/2024/CallForPapers
[2025]: https://iclr.cc/Conferences/2025/CallForPapers
