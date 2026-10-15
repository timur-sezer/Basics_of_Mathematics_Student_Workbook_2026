# Solution to Exercise 14: A 0/0 Limit with Trigonometry

## 1. Problem Statement

Compute the trigonometric limit:
$$
L = \lim_{x \to 0} \frac{1 - \cos x}{x^2}
$$

Justify the result rigorously without using l'Hôpital's rule, relying exclusively on trigonometric identities and the fundamental trigonometric limit $\lim_{u \to 0} \frac{\sin u}{u} = 1$.

---

## 2. Theoretical Background and Concepts

1. **Indeterminate Form $\frac{0}{0}$:**
   Direct evaluation at $x = 0$ yields:
   $$
   \frac{1 - \cos 0}{0^2} = \frac{1 - 1}{0} = \frac{0}{0}
   $$
   This is an indeterminate form of type $\frac{0}{0}$, requiring algebraic and trigonometric transformation to evaluate.

2. **The Fundamental Trigonometric Limit:**
   For any variable $u \to 0$:
   $$
   \lim_{u \to 0} \frac{\sin u}{u} = 1 \implies \lim_{u \to 0} \left(\frac{\sin u}{u}\right)^2 = 1^2 = 1
   $$

3. **Key Trigonometric Identities:**
   - **Pythagorean Identity & Conjugate Technique:**
     $$
     (1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x
     $$
     Multiplying numerator and denominator by the conjugate $(1 + \cos x)$ introduces $\sin^2 x$, which can be paired with $x^2$.
   - **Half-Angle Identity:**
     From the double-angle formula for cosine, $\cos(2\theta) = 1 - 2\sin^2\theta$, setting $2\theta = x$ gives:
     $$
     1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)
     $$

4. **Product Law of Limits:**
   If $\lim_{x \to c} f(x) = A$ and $\lim_{x \to c} g(x) = B$ (with finite limits $A, B$), then:
   $$
   \lim_{x \to c} [f(x) \cdot g(x)] = A \cdot B
   $$

---

## 3. Detailed Step-by-Step Solution

We present two complete and independent derivations using trigonometric identities and the fundamental limit.

### Method 1: The Conjugate Multiplication Method

1. **Multiply Numerator and Denominator by $(1 + \cos x)$:**
   For $x \neq 0$ and $x \in (-\pi, \pi)$, we have $1 + \cos x \neq 0$. Multiplying by $\frac{1 + \cos x}{1 + \cos x}$:
   $$
   \frac{1 - \cos x}{x^2} = \frac{(1 - \cos x)(1 + \cos x)}{x^2 (1 + \cos x)}
   $$

2. **Apply the Pythagorean Identity:**
   Using $(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x$:
   $$
   \frac{(1 - \cos x)(1 + \cos x)}{x^2 (1 + \cos x)} = \frac{\sin^2 x}{x^2 (1 + \cos x)}
   $$

3. **Factor and Regroup into Known Limits:**
   Split the expression into a product of factors:
   $$
   \frac{\sin^2 x}{x^2 (1 + \cos x)} = \left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}
   $$

4. **Apply Limit Laws:**
   Using the product law and continuity of $\cos x$ at $x = 0$:
   $$
   L = \lim_{x \to 0} \left[\left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}\right] = \left(\lim_{x \to 0} \frac{\sin x}{x}\right)^2 \cdot \lim_{x \to 0}\left(\frac{1}{1 + \cos x}\right)
   $$

5. **Evaluate the Individual Limits:**
   - $\lim_{x \to 0} \frac{\sin x}{x} = 1$
   - $\lim_{x \to 0} \frac{1}{1 + \cos x} = \frac{1}{1 + \cos 0} = \frac{1}{1 + 1} = \frac{1}{2}$

6. **Compute the Final Result:**
   $$
   L = 1^2 \cdot \frac{1}{2} = \frac{1}{2}
   $$

---

### Method 2: The Half-Angle Identity Method

1. **Substitute the Half-Angle Formula:**
   Recall that $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$. Substitute this into the limit expression:
   $$
   \frac{1 - \cos x}{x^2} = \frac{2\sin^2\left(\frac{x}{2}\right)}{x^2}
   $$

2. **Match the Argument in the Denominator:**
   The argument of the sine function is $u = \frac{x}{2}$. We need the denominator to contain $u^2 = \left(\frac{x}{2}\right)^2 = \frac{x^2}{4}$.
   Rewrite $x^2$ as $4 \cdot \left(\frac{x}{2}\right)^2$:
   $$
   \frac{2\sin^2\left(\frac{x}{2}\right)}{x^2} = \frac{2\sin^2\left(\frac{x}{2}\right)}{4 \cdot \left(\frac{x}{2}\right)^2} = \frac{2}{4} \cdot \left(\frac{\sin(x/2)}{x/2}\right)^2 = \frac{1}{2} \left(\frac{\sin(x/2)}{x/2}\right)^2
   $$

3. **Substitute $u = \frac{x}{2}$:**
   As $x \to 0$, $u \to 0$. By substitution:
   $$
   L = \lim_{x \to 0} \left[\frac{1}{2}\left(\frac{\sin(x/2)}{x/2}\right)^2\right] = \frac{1}{2} \left(\lim_{u \to 0}\frac{\sin u}{u}\right)^2
   $$

4. **Evaluate:**
   $$
   L = \frac{1}{2} \cdot (1)^2 = \frac{1}{2}
   $$

---

## 4. Verification and Consistency Checks

1. **Taylor Series / Maclaurin Expansion Verification:**
   The Maclaurin series for $\cos x$ about $x = 0$ is:
   $$
   \cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \mathcal{O}(x^6) = 1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots
   $$
   Substituting this into the numerator:
   $$
   1 - \cos x = 1 - \left(1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots\right) = \frac{x^2}{2} - \frac{x^4}{24} + \dots
   $$
   Dividing by $x^2$:
   $$
   \frac{1 - \cos x}{x^2} = \frac{1}{2} - \frac{x^2}{24} + \dots
   $$
   Taking $x \to 0$:
   $$
   \lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2}
   $$
   This completely agrees with our analytical solutions.

2. **L'Hôpital's Rule (Consistency Cross-Check):**
   Although avoided in the main proof as instructed, we verify using l'Hôpital's rule on the $\frac{0}{0}$ indeterminate form:
   - First application:
     $$
     \lim_{x \to 0} \frac{\frac{d}{dx}(1 - \cos x)}{\frac{d}{dx}(x^2)} = \lim_{x \to 0} \frac{\sin x}{2x} = \frac{1}{2}\lim_{x \to 0}\frac{\sin x}{x} = \frac{1}{2} \cdot 1 = \frac{1}{2}
     $$
   - Second application (if continued fully to non-indeterminate form):
     $$
     \lim_{x \to 0} \frac{\frac{d}{dx}(\sin x)}{\frac{d}{dx}(2x)} = \lim_{x \to 0} \frac{\cos x}{2} = \frac{\cos 0}{2} = \frac{1}{2}
     $$
   Both confirm $L = \frac{1}{2}$.

3. **Numerical Approximations:**
   Evaluating $f(x) = \frac{1 - \cos x}{x^2}$ at values approaching $0$:
   | $x$ | $\cos x$ | $1 - \cos x$ | $f(x) = \frac{1 - \cos x}{x^2}$ |
   |:---|:---|:---|:---|
   | $\pm 0.5$ | $0.87758256$ | $0.12241744$ | $0.48966975$ |
   | $\pm 0.1$ | $0.99500417$ | $0.00499583$ | $0.49958347$ |
   | $\pm 0.01$ | $0.99995000$ | $0.0000499996$ | $0.49999583$ |
   | $\pm 0.001$ | $0.99999950$ | $0.0000005000$ | $0.49999996$ |

   As $|x| \to 0$, $f(x)$ monotonically approaches $0.5 = \frac{1}{2}$ from below, exactly confirming the analytical result.
