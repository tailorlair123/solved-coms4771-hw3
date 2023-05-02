Download Link: https://assignmentchef.com/product/solved-coms4771-hw3
<br>
<ul>

 <li>[Bayesian interpretation of ridge regression] Consider the following data generating process for linear regression problem in R<em><sup>d</sup></em>. Nature first selects <em>d </em>weight coefficients <em>w</em><sub>1</sub><em>,…,w<sub>d </sub></em>as <em>w<sub>i </sub></em>∼ <em>N</em>(0<em>,τ</em><sup>2</sup>) i.d. Given <em>n </em>examples <em>x</em><sub>1</sub><em>,…,x<sub>n </sub></em>∈ R<em><sup>d</sup></em>, nature generates the output variable <em>y<sub>i </sub></em>as</li>

</ul>

<em>,</em>

where i.i.d.

Show that finding the coefficients <em>w</em><sub>1</sub><em>,…,w<sub>d </sub></em>that maximizes <em>P</em>[<em>w</em><sub>1</sub><em>,…,w<sub>d</sub></em>|(<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>)<em>…,</em>(<em>x<sub>n</sub>,y<sub>n</sub></em>)] is equivalent to minimizing the ridge optimization criterion.

<ul>

 <li>[Combining multiple classifiers] The concept of “wisdom-of-the-crowd” posits that collective knowledge of a group as expressed through their aggregated actions or opinions is superior to the decision of any one individual in the group. Here we will study a version of the “wisdom-of-the-crowd” for binary classifiers: how can one <em>combine </em>prediction outputs from multiple possibly low-quality binary classifiers to achieve an aggregate high-quality final output? Consider the following iterative procedure to combine classifier results.</li>

</ul>

Input:

<ul>

 <li><em>S </em>– a set of training samples: <em>S </em>= {(<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>)<em>,…,</em>(<em>x<sub>m</sub>,y<sub>m</sub></em>)}, where each <em>y<sub>i </sub></em>∈ {−1<em>,</em>+1}</li>

 <li><em>T </em>– number of iterations (also, number of classifiers to combine)</li>

 <li>F – a set of (possibly low-quality) classifiers. Each <em>f </em>∈ F, is of the form <em>f </em>: <em>X </em>→ {−1<em>,</em>+1}</li>

</ul>

Output:

<ul>

 <li><em>F </em>– a set of selected classifiers {<em>f</em><sub>1</sub><em>,…,f<sub>T</sub></em>}, where each <em>f<sub>i </sub></em>∈ F. – <em>A </em>– a set of combination weights {<em>α</em><sub>1</sub><em>,…,α<sub>T</sub></em>}</li>

</ul>

Iterative Combination Procedure:

<ul>

 <li>Initialize distribution weights</li>

 <li>for <em>t </em>= 1<em>,…,T </em>do</li>

 <li><strong>is weighted error of j-th classifier w.r.t. </strong><em>D<sub>t</sub></em></li>

 <li>Define [for each <em>f<sub>j </sub></em>∈ F]</li>

 <li><strong>// select the classifier with the smallest (weighted) error </strong>– <em>f<sub>t </sub></em>= argmin</li>

 <li><strong>// recompute weights w.r.t. performance of </strong><em>f<sub>t</sub></em></li>

 <li>Compute classifier weight</li>

 <li>Compute distribution weight <em>D<sub>t</sub></em><sub>+1</sub>(<em>i</em>) = <em>D<sub>t</sub></em>(<em>i</em>)exp(−<em>α<sub>t</sub>y<sub>i</sub>f<sub>t</sub></em>(<em>x<sub>i</sub></em>))</li>

 <li>Normalize distribution weights</li>

 <li>endfor</li>

 <li>return weights <em>α<sub>t</sub></em>, and classifiers <em>f<sub>t </sub></em>for <em>t </em>= 1<em>,…,T</em>.</li>

</ul>

Final Combined Prediction:

<ul>

 <li>For any test input <em>x</em>, define the aggregation function as: <em>g</em>(<em>x</em>) := <sup>P</sup><em><sub>t </sub></em><em>α<sub>t</sub>f<sub>t</sub></em>(<em>x</em>), and return the prediction as sign(<em>g</em>(<em>x</em>)).</li>

</ul>

We’ll prove the following statement: If for each iteration <em>t </em>there is some <em>γ<sub>t </sub>&gt; </em>0 such that

(that is, assuming that at each iteration the error of the classifier <em>f<sub>t </sub></em>is just <em>γ<sub>t </sub></em>better

than random guessing), then error of the aggregate classifier

err<em>.</em>

That is, the error of the aggregate classifier <em>g </em>decreases exponentially fast with the number of combinations <em>T</em>!

<ul>

 <li>Let <em>Z<sub>t </sub></em>:= <sup>P</sup><em><sub>i </sub></em><em>D<sub>t</sub></em><sub>+1</sub>(<em>i</em>) (i.e., <em>Z<sub>t </sub></em>denotes the normalization constant for the weighted distribution <em>D<sub>t</sub></em><sub>+1</sub>). Show that</li>

</ul>

<em>.</em>

<ul>

 <li>Show that error of the aggregate classifier <em>g </em>is upper bounded by the product of <em>Z<sub>t</sub></em>:</li>

</ul>

err(<em>g</em>) ≤ <sup>Q</sup><em><sub>t </sub></em><em>Z<sub>t</sub></em>.

(hint: use the fact that 0-1 loss is upper bounded by exponential loss)

<ul>

 <li>Show that.</li>

</ul>

(hint: noting <em>Z<sub>t </sub></em>= <sup>P</sup><em><sub>i </sub></em><em>D<sub>t</sub></em>(<em>i</em>)exp(−<em>α<sub>t</sub>y<sub>i</sub>f<sub>t</sub></em>(<em>x<sub>i</sub></em>)), separate the expression for correctly and incorrectly classified cases and express it in terms of

<ul>

 <li>By combining results from (ii) and (iii), we have that err, now show that:</li>

</ul>

<em>.</em>

Thus establishing that err(<em>g</em>) ≤ exp(−2<sup>P</sup><em><sub>t </sub></em><em>γ<sub>t</sub></em><sup>2</sup>).

<ul>

 <li>[Low-dimensionalinformation-preservingtransformations] (<em>hashingthecube</em>) You have a collection of nonzero distinct binary vectors <em>x</em><sub>1</sub><em>,…,x<sub>m </sub></em>∈ {0<em>,</em>1}<em><sup>n</sup></em>. To facilitate later lookup, you decide to hash them to vectors of length <em>p &lt; n </em>by means of a linear mapping <em>x<sub>i </sub></em>7→ <em>Ax<sub>i</sub></em>, where <em>A </em>is a <em>p </em>× <em>n </em>matrix with 0-1 entries, and all computations are performed modulo 2. Suppose the entries of the matrix are picked uniformly at random (ie, each an independent coin toss)

  <ul>

   <li>Pick any 1 ≤ <em>i </em>≤ <em>m</em>, and any <em>b </em>∈ {0<em>,</em>1}<em><sup>p</sup></em>. Show that the probability (over the choice of <em>A</em>) that <em>x<sub>i </sub></em>hashes to <em>b </em>is exactly 1<em>/</em>2<em><sup>p</sup></em>. (Hint: focus on a coordinate 1 ≤ <em>j </em>≤ <em>n </em>for which <em>x<sub>ij </sub></em>= 1.)</li>

   <li>Pick any 1 ≤ <em>i &lt; j </em>≤ <em>m</em>. What is the probability that <em>x<sub>i </sub></em>and <em>x<sub>j </sub></em>hash to the same vector? This is called a <em>collision</em>.</li>

   <li>Show that if <em>p </em>≥ 2log<sub>2 </sub><em>m</em>, then with probability at least 1<em>/</em>2, there are no collisions among the <em>x<sub>i</sub></em>. Thus: to avoid collisions, it is enough to linearly hash into <em>O</em>(log<em>m</em>) dimensions!</li>

  </ul></li>

</ul>

(question credit: Prof. Sanjoy Dasgupta)

<ul>

 <li>[Strange consequences of high dimensionality] As discussed in class, we often represent our data in high dimensions. Thus to understand our data better and design effective prediction algorithms, it is good to understand how things behave in high dimensions. Obviously, since we cannot visualize or imagine high dimensional spaces, we often tend to rely on how data behave in one-, two- or three-dimensions and extrapolate how they may behave in hundreds of dimensions. It turns out that our low dimensional intuition can be very misleading about data and distributions in high dimensional spaces. In this problem we will explore this in more detail.</li>

</ul>

Consider the Gaussian distribution with mean <em>µ </em>and identity covariance <em>I<sub>d </sub></em>in R<em><sup>d</sup></em>. Recall that the density assigned to any point <em>x </em>∈ <em>R<sup>d</sup></em>, then becomes

<em>.</em>

<ul>

 <li>Show that when <em>x </em>= <em>µ</em>, <em>x </em>gets assigned the highest density.</li>

</ul>

(This, of course, makes sense: the Gaussian density peaks at its mean and thus <em>x </em>= <em>µ </em>has the highest density.)

<ul>

 <li>If mean has the highest density, it stands to reason that if we draw a large i.i.d. sample from the distribution, then a large fraction of the points should lie close to the mean. Let’s try to verify this experimentally. For simplicity, let mean <em>µ </em>= 0 (covariance is still <em>I<sub>d</sub></em>). Draw 10,000 points i.i.d. from a Gaussian <em>N</em>(0<em>,I<sub>d</sub></em>).</li>

</ul>

To see how far away a sampled datapoint is from the mean, we can look at the distance k<em>x </em>− <em>µ</em>k<sup>2 </sup>= k<em>x</em>k<sup>2 </sup>(that is, the squared length of the sampled datapoint, when mean is zero). Plot the histogram of squared length of the samples, for dimensions <em>d </em>= 1<em>,</em>2<em>,</em>3<em>,</em>5<em>,</em>10<em>,</em>50 and 100. You should plot the all these histograms on the same figure for a better comparison.

What interesting observations do you see from this plot? Do you notice anything strange when the samples that were drawn from the high dimensional Gaussian distribution? Do most of the samples lie close to the mean?

<ul>

 <li>Let’s mathematically derive where we <em>expect </em>these samples to lie. That is, calculate</li>

</ul>

E<em>x</em>∼<em>N</em>(0<em>,I<sub>d</sub></em>)hk<em>x</em>k2i<em>.</em>

Is the empirical plot in part (ii) in agreement with the mathematical expression you derived here?

<ul>

 <li>This “strangeness” is not specific to Gaussian distribution, you can observe something similar even for the simplest of distributions in high dimensions. Consider the uniform distribution over the cube [−1<em>,</em>1]<em><sup>d</sup></em>. Just like in part (ii), draw 10,000 i.i.d. samples from this <em>d</em>-dimensional cube with uniform density, and plot the histogram of how far away from the origin the sample points lie. (do this for <em>d </em>= 1<em>,</em>2<em>,</em>3<em>,</em>5<em>,</em>10<em>,</em>50 and 100, again on the same plot).</li>

</ul>

Recall that the cube has side length of 2, while most of the high-dimensional samples have length of far more than 2! This means even though you are drawing uniformly from the cube, most of your samples lie in the corners (and not the interior) of the cube!

<ul>

 <li>Again, calculate the expected (squared) length of the samples. That is, calculate</li>

</ul>

E<em>x</em>∼unif([−1<em>,</em><sub>1]</sub><em><sup>d</sup></em><sub>)</sub><sup>h</sup>k<em>x</em>k2<sup>i</sup><em>.</em>

Does the plot in part (iv) in agreement with the expression you derive here?