# Dataset: Opus NLPL

Little script to download corpora from [Opus NLPL](http://opus.nlpl.eu/) using this lovely [utility](https://github.com/Helsinki-NLP/OpusTools).

Install `opustools`:

```bash
pip install opustools
```

The site continues to add more datasets, but as of 04/2021 the downloading size
(gzipped) was 28 GB for French only (gzipped), downloading all the monolingual
raw resources (untokenized). The script is meant to be run once, gathering,
gunzipping, and removing the archives in the process. It is not optimized to
handle all use cases (e.g. interrupted downloads, where one might have manually
to delete the partially retrieved archives, etc.).

---

Usage:

```bash
python download.py --help
usage: download.py [-h] [-l LANGUAGE] [-dl DOWNLOAD_DIR] [-i] [-g] [-r]

Downloading all datasets from Opus: http://opus.nlpl.eu/. This is meant for language modelling rather than
translation: the aim is to get large amounts of plain text, rather than language pairs.

optional arguments:
  -h, --help            show this help message and exit
  -l LANGUAGE, --language LANGUAGE
                        The language code chosen. Defaults to 'fr'.
  -dl DOWNLOAD_DIR, --download_dir DOWNLOAD_DIR
                        The directory to be downloaded into. Defaults to 'opus'.
  -i, --list            Lists all resources available instead of downloading. Defaults to false.
  -g, --no_gunzip       Do not gunzip the files after downloading. Defaults to false.
  -r, --no_remove_gz    Do not remove gzip files after gunzipping. Defaults to false.
```
