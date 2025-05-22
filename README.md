[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Create TF entropy feature

This repository contains the [Jupyter Notebook](Feature_creation_betacode_for_N1904-TF_dataset.ipynb) used to create three new Text-Fabric feature:

   - [lemma_entr](): Entropy for lemma to parent phrase function in the N1904-TF corpus
   - [morph_entr](): Entropy for morph to parent phrase function in the N1904-TF corpus
   - [text_entr](): Entropy for surface text to parent phrase function in the N1904-TF corpus
   
The final feature files will be added to the package available at the [tonyjurg/N1904addons](https://tonyjurg.github.io/N1904addons/) repository.

## About Text-Fabric

The Text-Fabric framework is designed to facilitate the analysis and manipulation of large-scale textual data, particularly in the context of ancient languages and biblical texts. The engine of Text-Fabric is its powerful Python library, which provides a comprehensive set of tools for processing and querying structured text data efficiently. The software package is accessible at [https://github.com/annotation/text-fabric](https://github.com/annotation/text-fabric).

## Documentation

[prelimenair documentation](docs/entropy_feature.md)

## Attribution and footnotes

The Greek base text is from Nestle1904 Greek New Testament, edited by Eberhard Nestle, published in 1904 by the British and Foreign Bible Society:
> Nestle, Eberhard. Η Καινή Διαθήκη Novum Testamentum Graece (New York: Fleming H. Revell Company, 1904).
The 1913 reprint is available [here](https://archive.org/details/hkainediathekete00lond/), which was transcribed by [Diego Santos](https://sites.google.com/site/nestle1904/home). All this material is in Public domain.


The [N1904-TF dataset](https://centerblc.github.io/N1904/) available under [MIT license](https://github.com/CenterBLC/N1904/blob/main/LICENSE.md). Formal reference: 
> Tony Jurg, Saulo de Oliveira Cantanhêde, & Oliver Glanz. (2024). *CenterBLC/N1904: Nestle 1904 Text-Fabric data*. Zenodo. DOI: [10.5281/zenodo.13117911](https://doi.org/10.5281/zenodo.13117910).

## License

This notebook is released under the [MIT License, Copyright © 2025 Tony Jurg](https://github.com/tonyjurg/create_TF_feature_betacode/blob/main/LICENSE.md)

## Citation

If you use this repository in your academic work, please [cite it](CITATION.cff).

