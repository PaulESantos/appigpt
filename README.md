
<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
[![CRAN
status](https://www.r-pkg.org/badges/version/apigpt)](https://CRAN.R-project.org/package=apigpt)
[![R-CMD-check](https://github.com/PaulESantos/apigpt/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/PaulESantos/apigpt/actions/workflows/R-CMD-check.yaml)
[![Codecov test
coverage](https://codecov.io/gh/PaulESantos/apigpt/branch/main/graph/badge.svg)](https://app.codecov.io/gh/PaulESantos/apigpt?branch=main)
<!-- badges: end -->

The goal of apigpt is easily incorporate large language models (LLMs)
into my project workflows, based on
[gptstudio](https://github.com/MichelNivard/gptstudio) R package,
changing the original code for doing Spanish tasks.

These models appear to be a step change in our use of text for knowledge
work, but you should consider the ethical implications of using these
models. The ethics of LLMs (also called [Foundation
Models](https://arxiv.org/abs/2108.07258)) is an area of very active
discussion.

**read the privacy note at the bottom, this is alpha software there is
no warranty for anything.**

## Prerequisites

1.  Make an OpenAI account. As of now, the free one will do.

2.  [Create an OpenAI API key](https://beta.openai.com/account/api-keys)
    to use `{openai}` package within Rstudio

3.  Set the API key up in Rstudio in one of two ways:

- By default, functions of `{openai}` will look for `OPENAI_API_KEY`
  environment variable. If you want to set a global environment
  variable, you can use the following command, where `"<APIKEY>"` should
  be replaced with your actual key:

``` r
Sys.setenv(OPENAI_API_KEY = "<OPENAI_API_KEY>")
```

- Alternatively, you can set the key in your .Renviron file.

Otherwise, you can add the key to the .Renviron file of the project. The
following commands will open .Renviron for editing:

``` r
require(usethis)
edit_r_environ(scope = "project")
```

You can add the following line to the file (again, replace
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx with your actual
key):

``` bash
OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

This now set the API key every time you start up this particular
project. Note: If you are using GitHub/Gitlab, do not forget to add
.Renviron to .gitignore!

## Install the addins from this package:

``` r
require(pak)
pak::pak("PaulESantos/apigpt")
```

**Addins \> GPTSTUDIO \> Spelling and Grammar:** Takes the selected text
sends it to OpenAI’s best model and instructs it to return a spelling
and grammar checked version.

**Privacy note:** these functions work by taking the text or code you
have highlighted/selected with the cursor and send these to OpenAI as
part of a prompt, they fall under their privacy notice/rules/exceptions
you agreed to with OpenAI when making an account. I do not know how
secure these are when sent to OpenAI, I also don’t know what OpenAI does
with them. The code is designed to ONLY share the highlighted/selected
text and no other elements of your R environment (i.e. data) unless you
have highlighted it when running the addin. This may limit usability for
now, but I do not want people to accidentally share sensitive data with
OpenAI.

DO NOT HIGHLIGHT, AND THEREFORE UPLOAD, DATA/CODE/TEXT THAT SHOULD
REMAIN PRIVATE.

## Usage

Some examples of use.

1.  **Spanish spelling and grammar check**
