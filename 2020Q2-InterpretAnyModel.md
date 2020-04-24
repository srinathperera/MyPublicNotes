https://blog.acolyer.org/2016/09/22/why-should-i-trust-you-explaining-the-predictions-of-any-classifier/
Interpreting a model might be great way to debug and improve - https://blog.acolyer.org/2016/09/22/why-should-i-trust-you-explaining-the-predictions-of-any-classifier/ & https://github.com/marcotcr/lime

* idea: overall the shape of the curve may be very complex, but if we look at just a small part we can figure out the gradient in that region.
* The LIME algorithm produces Local Interpretable Model-agnostic Explanations.
* For text classification, an interpretable representation could be a vector indicating the presence or absence of a word, even though the classifier may use more complex word embeddings. For image classification an interpretable representation might be an binary vector indicating the ‘presence’ or ‘absence’ of a contiguous patch of similar pixels.
* LIME works by drawing samples in the vicinity of the input to be explained and learning a linear classifier using locally weighted square loss, with a limit K set on the number of interpretable features.
* Since [the algorithm] produces an explanation for an individual prediction, its complexity does not depend on the size of the dataset, but instead on time to compute f(x) [a model prediction] and on the number of samples N. In practice, explaining random forests with 1000 trees using scikit-learn on a laptop with N = 5000 takes under 3 seconds without any optimizations such as using gpus or parallelization. Explaining each prediction of the Inception network for image classification takes around 10 minutes.
* The central idea here is that if we understand and trust the reasoning behind an individual prediction, and we repeat this process for a number of predictions that give good coverage of the input space, then we can start to build global trust in the model itself.