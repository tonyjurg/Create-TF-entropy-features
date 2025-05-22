# preliminairy documentation

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

To demonstrate how the entropy is determined, let us consider the form "λόγος" (N-NSM; a Nominative Singular Masculine Noun).

Of the 63 occurenses in the N1904-TF dataset it is:

  * 55 times as part of a `Subject` phrase
  * 3 times as part of a `Predicate Complement` phrase 
  * 2 time as part of a `Conjunction` phrase  {this is under investigation}
  * 2 times as part of a phrase labeled as 'Unknown' {this is under investigation}
  * 1 time as part of a `Predicate` phrase


First, we can calculate the probabilities:

- $P(Subj|\text{λόγος}) = 55 / 63 = 0.873015873015873$
- $P(PreC|\text{λόγος}) = 3 / 63 = 0.047619047619047616$
- $P(Pred|\text{λόγος}) = 1 / 63 = 0.015873015873015872$
- $P(Conj|\text{λόγος}) = 2 / 63 = 0.031746031746031744$
- $P(Unkn|\text{λόγος}) = 2 / 63 = 0.031746031746031744$

Next we can compute the entropy: 

$$ Entropy = - (P(Subj|\text{λόγος}) \cdot \log_2 P(Subj|\text{λόγος}) + P(PreC|\text{λόγος}) \cdot \log_2 P(PreC|\text{λόγος}) + P(Conj|\text{λόγος}) \cdot \log_2 P(Conj|\text{λόγος}) + P(Unkn|\text{λόγος}) \cdot \log_2 P(Unkn|\text{λόγος}) + P(Pred|\text{λόγος}) \cdot \log_2 P(Pred|\text{λόγος})) $$

If we calculate each term we get: 

- For $P(Subj|\text{λόγος}) = 0.873015873015873$, $\log_2 0.873015873015873 \approx -0.1905$. So, $0.873015873015873 \cdot -0.1905 \approx -0.1663$.
- For $P(PreC|\text{λόγος}) = 0.047619047619047616$, $\log_2 0.047619047619047616 \approx -4.392$. So, $0.047619047619047616 \cdot -4.392 \approx -0.2093$.
- For $P(Conj|\text{λόγος}) = 0.031746031746031744$, $\log_2 0.031746031746031744 \approx -4.974$. So, $0.031746031746031744 \cdot -4.974 \approx -0.1581$.
- For $P(Unkn|\text{λόγος}) = 0.031746031746031744$, same as above, $-0.1581$.
- For $P(Pred|\text{λόγος}) = 0.015873015873015872$, $\log_2 0.015873015873015872 \approx -6.322$. So, $0.015873015873015872 \cdot -6.322 \approx -0.1004$.

So the final entropy can be calculated as:

$$ Entropy = - (-0.1663 - 0.2093 - 0.1581 - 0.1581 - 0.1004) $$
$$ Entropy = - (-0.7922) $$
$$ Entropy = 0.7922 $$

This matches what was found by the calculations performe in our notebook, which used float numbers (instead of the rounded ones above):

```python
>>> entropies_by_datatype['text']['λόγος']
'0.7910'
```


That’s a relatively low entropy, meaning the morphological form “λόγος” is strongly predictive of being a subject.

It is important to realize that each words entropy is measured against the whole of the N1904-TF corpus (which is 'hidden' in the $P(f|m)$ of the formal definition). It is likely that the values for entropy of the same morp are different when considered within another corpus.

