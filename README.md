# Markdown Meeting Notes → Google Doc (Google Colab + Docs API)

This project converts markdown meeting notes into a well-formatted Google Doc using the Google Docs API. It supports headings, nested bullet lists, markdown checkboxes, @mentions styling, and a styled footer section.

## What it does

* Creates a new Google Doc programmatically
* Applies:

  * Heading 1 for the title
  * Heading 2 for sections
  * Heading 3 for sub-sections
* Preserves nested bullet hierarchy
* Converts `- [ ]` tasks into Google Docs checkboxes
* Styles @mentions (bold + colored)
* Styles footer lines (smaller, gray, italic)

## Setup

### Requirements

* Google Colab (recommended)
* Python 3
* Google Docs API access (handled via Colab auth)

### Dependencies

In Colab, these are available by default:

* `google-api-python-client`
* `google-auth`
* `google-colab`

If running outside Colab, install:

```bash
pip install google-api-python-client google-auth google-auth-oauthlib
```

## How to run in Colab

1. Open the notebook: `notebooks/markdown_to_gdoc.ipynb`
2. Run all cells
3. When prompted, sign in with Google
4. The output cell prints the new document URL

## Repo structure (suggested)

* `notebooks/markdown_to_gdoc.ipynb`
* `src/markdown_to_gdoc.py`
* `README.md`

## Notes

* Checkbox bullets use the Google Docs `BULLET_CHECKBOX` preset.
* Indentation is inferred from leading spaces in markdown bullets (2 spaces per nesting level).
