# Home
## Welcome to the Third-Party Developer(s) Documentation for EVE Online.
This is a new community supported repository for instructions and guidance that is useful for those making third-party tools for EVE.

It is intended to always be a living document, and the plan is for it to be frequently updated to reflect changes in the APIs and/or services.

## Deprecation notice
As of [this blog post](https://community.eveonline.com/news/dev-blogs/introducing-esi/) made on November 18th, 2016 it was announced that CCP's newest
API -- ESI -- was going to replace the XML API and CREST. It was also announced that **CREST and XML API are going to be shut down by May 8th, 2018, or earlier if metrics signal a trivial level of usage**. This
means three things:

1. If you have never developed against an EVE Online API before and you are looking at creating a new tool/app based around EVE, **Do not use CREST or
   XML API**. Please use [ESI](esi/index.md).
2. If you have tools/apps made against XML API or CREST then you will need to migrate to ESI before May 8th, 2018.
3. If the XML API or CREST's traffic dwindles to trivial usage they will be shut down earlier than May 8th, 2018.


## Contributing
There is a lot of work to be done on this site and any contributions are welcome. The docs are hosted on a [GitHub repository](https://github.com/ccpgames/eveonline-third-party-documentation), where anyone can fork it, commit changes and submit a pull request to get your changes onto the site.

The source files are written in markdown, which is very easy to get started using. There is a fairly good introduction to markdown available from [GitHub](https://guides.github.com/features/mastering-markdown/).

Please follow the `recommonmark` guidelines for [math formulas](https://recommonmark.readthedocs.io/en/latest/auto_structify.html#math-formula) and [inline math](https://recommonmark.readthedocs.io/en/latest/auto_structify.html#inline-math).

There is a contributors file, as well as more info on contributing to the documentation on the repository.

* [ESI](esi/index.md)
* [Guidelines and References](reference/index.md)
* [Single Sign-On (SSO)](sso/index.md)
* [Formulas](formulas/index.md)
* [Static Data Export](sde/index.md)
* [Dogma](dogma/index.md)
* [Image Server](imageserver/index.md)
* [Deprecated: CREST](crest/index.md)
* [Deprecated: XML API](xmlapi/index.md)
