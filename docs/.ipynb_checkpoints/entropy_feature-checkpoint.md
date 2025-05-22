Idea: lets move this feature separate from the Morpheus set

In our Text-Fabric morphology-based setup entropy measures the uncertainty or variability in how a word predicts or aligns with syntactic functions (like Subject, Object, etc.).

If a word (or more precisely, its morphological form) can lead to multiple functions with different probabilities, its entropy is high — meaning there's ambiguity. If it clearly and consistently points to one function, entropy is low — meaning it's a reliable indicator. 

## Formal Definition

The feature value was calculated using *Shannon entropy*, defined as:

$$
H(f|m) = -\sum_{f \in F} P(f|m) \cdot \log_2 P(f|m)
$$

Where:

* $m$ = a specific morphological form (like `N-NSM`)
* $f$ = a syntactic function (like `Subj`, `Objc`, etc.)
* $P(f|m)$ = the probability that form $m$ leads to function $f$

This gives a measure (in bits) of how unpredictable the function is for a given morph.

## Example from the N1904-TF dataset

Let us consider the form "λόγος" (N-NSM; a Nominative Singular Masculine Noun) occurs 50 times:

* 40 times as `Subject`
* 5 times as `Predicate`
* 5 times as something else

Then:

* $P(Subj|\text{λόγος}) = 40 / 50 = 0.8$
* $P(PreC|\text{λόγος}) = 5 / 50 = 0.1$
* $P(Other|\text{λόγος}) = 5 / 50 = 0.1$

Entropy =

$$ - (0.8 \cdot \log_2 0.8 + 0.1 \cdot \log_2 0.1 + 0.1 \cdot \log_2 0.1) ≈ 0.92 \text{ bits}$$

That’s a relatively low entropy, meaning the morphological form “λόγος” is strongly predictive of being a subject.

It is important to realize that each words entropy is measured against the whole of the N1904-TF corpus (which is 'hidden' in the $P(f|m)$ of the formal definition). It is likely that the values for entropy of the same morp are different when considered within another corpus.

