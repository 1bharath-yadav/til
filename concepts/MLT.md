- https://discourse.onlinedegree.iitm.ac.in/t/mlt-ta-session-resources-may-2025-term/175138
- https://bsc-iitm.github.io/MLT_notes/'
-
-
- # Term1-unsupervised learning
- # Term2-Supervised learning
	-
	- ### Linear regression
		- we are given samples $X \in\mathbb{R}^{d \times n}$ matrix and labels $y \in \mathbb{R}^{n \times 1}$  matrix and we have to find which weight matrix $W \in \mathbb{R}^{d \times 1}$.
		- $X \times w \neq y$
		- $d \times n \cdot d \times 1 \neq n \times 1$ y can't be obtain by projecting single feature of all datapoints on to w(null space) as y is the manupulation of feature space which is column space of X
		- So,  we do $X{^T}  \cdot w = y$ now we can get corresponding $y^{th}$ feature by transforming corresponding feature  with weight vector by multiplying certain weights to corresponding  feature.look y as new sample with features space same as X and we can get this new sample y by transforming the featurespace of already existed data X
		- the perfect parameters/coefficiesnts/weights that makes our sample features transformation suitable for our new data features  may not exist though both are in same feature space.
		- $$
		  \begin{aligned}
		  X^Tw-y &=0 \\
		  (X^Tw-y) \cdot X &= 0 \\
		  XX^Tw-Xy &=0 \\
		  W^* &= XX^{+} Xy
		  \end{aligned}
		  $$
		-
		-
		- the loss function is $L(w) = \sum_{i=1}^{n} (w^T x_i - y_i)^2$
		- this is convex function and objetive function that we want to minimize to get best W so
		- $$
		  \begin{aligned}
		  L(w) &= \sum_{i=1}^{n} (w^T x_i - y_i)^2 \\
		  \nabla_w L(w) &= \nabla_w \sum_{i=1}^{n} (w^T x_i - y_i)^2 \\
		  &= \sum_{i=1}^{n} \nabla_w (w^T x_i - y_i)^2 \\
		  &= \sum_{i=1}^{n} 2(w^T x_i - y_i) \cdot \nabla_w (w^T x_i - y_i) \\
		  &= \sum_{i=1}^{n} 2(w^T x_i - y_i) x_i \\
		  \end{aligned}
		  $$
		  $$
		  \begin{aligned}
		  \text{To minimize } L(w)\text{, set } \nabla_w L(w) = 0: \\
		  \sum_{i=1}^{n} 2(w^T x_i - y_i) x_i &= 0 \\
		  \sum_{i=1}^{n} (w^T x_i - y_i) x_i &= 0 \\
		  \sum_{i=1}^{n} (x_i w^T x_i - y_i x_i) &= 0 \\
		  \sum_{i=1}^{n} (x_i x_i^T w - y_i x_i) &= 0 \quad \text{(Assuming } x_i^T w = w^T x_i \text{ is a scalar and } x_i \text{ is a column vector)} \\
		  \sum_{i=1}^{n} x_i x_i^T w &= \sum_{i=1}^{n} y_i x_i \\
		  (X^T X) w &= X^T y \quad \text{(Matrix form, where } X \text{ has } x_i^T \text{ as rows and } y \text{ has } y_i \text{ as elements)} \\
		  w &= (X^T X)^{-1} X^ y \\
		  \end{aligned}
		  $$
		-
		- we can find w with this equation but the inverse and dxd computations is much more \
		- so we wiil try Gradient descent
		- $$w_{t+1}=w_t + \alpha(-( \nabla_w L(w))$$
		- $$w_t+1 = w_t  - \alpha (XX^Tw^t-Xy)$$
		-
		- here also we have to compute dxd matrix, computationally expensive
		- then stochastic grradient descent comes wich takes batches randomly from datapoints
		- $$w_t+1 = w_t  - \alpha (X'X'^Tw^t-X'y)$$
		- [summary](file:///home/archer/Documents/IITMCLASS/term3/MLT/Summary/Week-5-summary.pdf)
		- it takes every datapoint into account so its normally overfit the model
	- ### Regularization
		- https://chatgpt.com/c/688aef2e-f080-8002-a23d-e0eaa01913a1
		- [Regularization](file:///home/archer/Documents/IITMCLASS/term3/MLT/Summary/Week-6-summary.pdf)
		-
	-
		-
- Naive Bayes Classification
	- number of parameters required =$$(C-1)  + \sum_{j=1}^F (k_j-1) \times C$$
	- prior propabalities + sum of the product of number of feature values -1 and number of classes of all features
	-
	-
	-