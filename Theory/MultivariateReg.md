## Linear Regression Algorithm (Multivariate)
- Multiple features (x1, x2, x3) (n)
- Hypothesis includes multiple components
<p align="center"><img src="images/multivar.png" width="250"></p>

### Gradient Descent Algorithm For Multiple Variables
- Multiple features to constantly update 

#### Implementing Gradient Descent Well: Feature Scaling
- Features should have similar ranges of values (0-2000) and (0-5)
- Scaling would make contours of cost function more circular -> gradient decent takes direct path to global minimum (size/2000) and (# of rooms/5)
- Each feature have range: -1 <= x <= 1 (Close enough to this range should have efficient algorithm), (not too small or not too large)
- #### Mean Normalization
    - Take average: (testSize - avgSize) / (maxSize - minSize)
    - avgSize = average value of x in training set

#### Implementing Gradient Descent Well: Learning Rate (choosing 𝛼)
- Make sure gradient descent is working well
- Plot # iterations vs cost function -> should decrease and converge to a value
- Convergence if J(θ) decreases less than 10^-3
- **J(θ) increasing -> smaller 𝜶**
- **J(θ) a parabola, -> overshoots if bigger 𝛼**
- **J(θ) slow to converge -> 𝛼 too small**

### Polynomial Regression
- Use powers and roots in features to fit curve that models data
<p align="center"><img src="images/graphPoly.png" width="250"></p>

### Normal Equation Non Invertibilty
- Using normal function to find value of θ without gradient descent: 
<p align="center"><img src="images/normalequation.png" width="250"></p>

- **Matrices that do not have inverses: degenerate or non-invertible**
- if (X^T X == non-invertible) -> **simplify features (redundant features)** or **delete some features (regularization)**
- Inverse of matrix in octave: "pinv()"

### Gradient Descent vs Normal Equation
- **Gradient Descent** -> taking steps to minimize J(θ) and find the global minimum θ
- **Normal Equation** -> Solve for optimal value θ
- To get normal equation, solve for each feature in J(θ)
- Normal Equation does not need Feature Scaling
- When to use and not use both methods:
<p align="center"><img src="images/GDvsNE.png" width="250"></p>