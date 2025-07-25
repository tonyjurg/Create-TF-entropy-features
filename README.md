[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

# Create TF entropy features

This repository contains the Jupyter Notebook used to create three new Text-Fabric feature:

   - [lemma_entr_mbit](https://tonyjurg.github.io/N1904addons/features/lemma_entr_mbit.html): Absolute entropy of the lemma as predictor of its parent phrase function in milibits.
   - [morph_entr_mbit](https://tonyjurg.github.io/N1904addons/features/morph_entr_mbit.html): Absolute entropy of the morph as predictor of its parent phrase function in milibits.
   - [text_entr_mbit](https://tonyjurg.github.io/N1904addons/features/text_entr_mbit.html): Absolute entropy of the surface level wordform as predictor of its parent phrase function in milibits.
   - [lemma_entr_norm](https://tonyjurg.github.io/N1904addons/features/lemma_entr_norm.html): Normalized entropy of the lemma as predictor of its parent phrase function in range [0,1].
   - [morph_entr_norm](https://tonyjurg.github.io/N1904addons/features/morph_entr_norm.html): Normalized entropy of the morph as predictor of its parent phrase function in range [0,1].
   - [text_entr_norm](https://tonyjurg.github.io/N1904addons/features/text_entr_norm.html): Normalized entropy of the surface level wordform as predictor of its parent phrase function in range [0,1].
   
The final feature files will be added to the package available at the [tonyjurg/N1904addons](https://tonyjurg.github.io/N1904addons/) repository.

## Production notebook

You can view the production notebook on [nbviewer.org](https://nbviewer.org/github/tonyjurg/Create-TF-entropy-features/blob/main/create_entropy_type2pf_features.ipynb).

Alternative, you can also download it from the [GitHub repository](https://github.com/tonyjurg/Create-TF-entropy-features/blob/main/create_entropy_type2pf_features.ipynb).

## About Text-Fabric

The Text-Fabric framework is designed to facilitate the analysis and manipulation of large-scale textual data, particularly in the context of ancient languages and biblical texts. The engine of Text-Fabric is its powerful Python library, which provides a comprehensive set of tools for processing and querying structured text data efficiently. The software package is accessible at [https://github.com/annotation/text-fabric](https://github.com/annotation/text-fabric).

## Documentation

See the individual features.

## Attribution and footnotes

The Greek base text is from Nestle1904 Greek New Testament, edited by Eberhard Nestle, published in 1904 by the British and Foreign Bible Society:
> Nestle, Eberhard. Η Καινή Διαθήκη Novum Testamentum Graece (New York: Fleming H. Revell Company, 1904).
The 1913 reprint is available [here](https://archive.org/details/hkainediathekete00lond/), which was transcribed by [Diego Santos](https://sites.google.com/site/nestle1904/home). All this material is in Public domain.


The [N1904-TF dataset](https://centerblc.github.io/N1904/) available under [MIT license](https://github.com/CenterBLC/N1904/blob/main/LICENSE.md). Formal reference: 
> Tony Jurg, Saulo de Oliveira Cantanhêde, & Oliver Glanz. (2024). *CenterBLC/N1904: Nestle 1904 Text-Fabric data*. Zenodo. DOI: [10.5281/zenodo.13117911](https://doi.org/10.5281/zenodo.13117910).

## License

This repository is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://github.com/tonyjurg/Create-TF-entropy-features/blob/main/LICENSE.md)

## Citation

If you use this repository in your academic work, please [cite it](CITATION.cff).

