# Summarize
Command-line interface to summarization pipelines, powered by Huggingface transformers.
This tool will download a multi-language summarization model, which is about 2GB large.
After that, it can be used to create abstracts of articles or summaries of all sorts.

## Install

```bash
$ git clone https://github.com/Teuze/summarize
$ cd summarize
$ pip3 install --user -r requirements.py
```
If you want to be able to use this script from anywhere in your system, you can symlink or copy the `summarize` script file into one of your path folders, like for example `$HOME/.local/bin`.

## Usage

Downloading model :

```bash
$ ./summarize init
```

Listing supported languages :

```bash
$ ./summarize lang list
```

Using model to summarize from text file or from standard input :

```bash
$ ./summarize file -s 80 examples/article.es.txt
Los gobiernos británicos y canadienses se reúnen este lunes para discutir el acuerdo final de la cumbre del clima de Glasgow.
$ cat examples/article.fr.txt | ./summarize text
La Pologne a annoncé lundi avoir arrêté des dizaines de migrants en provenance de Biélorussie.
```

Note : you can use option `-L` (or `--lang`) to explicitly define the input text language.
However, this will only check against currently supported languages and throw an error if unknown.
The summarization model in itself does not need to be told which language it is.
