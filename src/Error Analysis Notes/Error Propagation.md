# Error Propagation
Author: [yihung](johnsonlin0528.c@nycu.edu.tw)
_ _ _
## Why we use Error propagate
![[https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/Error%20Analysis%20Notes/img/snapshot.png]]
[(source)](https://www.youtube.com/watch?v=V0ZRvvHfF0E)

當我們要計算動能的精確值時，會需要使用到質量跟速度這兩個物理量，而我們在得到這兩個物理量時可能因為儀器或其他原因，而導致得到物理量有誤差，而我們為了想準確的知道這些誤差會帶給動能有什麼影響，因此需要利用誤差傳遞。

## Derived formula
在這裡我們把導出量設為 $X$,而直接測到的量為 $u$,$v$ 則可以寫成函數式：
$$
X = f\left(u, v\right)
$$
$\bar{u}$, $\bar{v}$分別代表 $u$, $v$ 的平均值,
$$
\bar{X} = f\left(\bar{u}, \bar{v}\right)
$$
對於某一組測量樣本數據，可以表示為：
$$X_{i} = f\left(u_{i}, v_{i}\right)$$


### Definition:
$$\sigma_{X}^{2}=\lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2}$$
推導
$$
\begin{align}
X_{i}-\bar{X}
&=
  f\left(u_{i}, v_{i}\right)-f(\bar{u}, \bar{v})
\\[1.5ex]
&=
  \left[f(\bar{u}, \bar{v})+\left(\frac{\partial f}{\partial u}\right)_{\bar{u}}\left(u_{i}-\bar{u}\right)+\left(\frac{\partial f}{\partial v}\right)_{\bar{v}}\left(v_{i}-\bar{v}\right)\right]-f(\bar{u}, \bar{v})
\\[1.5ex]
&=
   \left(\frac{\partial f}{\partial u}\right)_{\bar{u}}\left(u_{i}-\bar{u}\right)+\left(\frac{\partial f}{\partial v}\right)_{\bar{v}}\left(v_{i}-\bar{v}\right)
\\[1.5ex]
&=
\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}\left(u_{i}-\bar{u}\right)+\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}\left(v_{i}-\bar{v}\right)
\end{align}
$$

把以上結果代入
$$
\begin{align}
\sigma_{X}^{2} &=
    \lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left(X_{i}-\bar{X}\right)^{2}
\\[1.5ex]
&=
    \lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left[\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}\left(u_{i}-\bar{u}\right)+\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}\left(v_{i}-\bar{v}\right)\right]^{2}
\\[1.5ex]
&=
\lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left[\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}^{2}\left(u_{i}-\bar{u}\right)^{2}+\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}^{2}\left(v_{i}-\bar{v}\right)^{2}+2\left(u_{i}-\bar{u}\right)\left(v_{i}-\bar{v}\right)\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}\right]
\\[1.5ex]
&=
  \sigma_{u}^{2}\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}^{2}+\sigma_{v}^{2}\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}^{2}+2 \sigma_{u v}^{2}\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}
\end{align}
$$


由上式可知
$$
\begin{align}
\sigma_{u}^{2} &= 
	\lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left(u_{i}-\bar{u}\right)^{2},
\\[1.5ex]
\sigma_{v}^{2} &=
	\lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left(v_{i}-\bar{v}\right)^{2},
\\[1.5ex]
\sigma_{u v}^{2} &=
	\lim _{\mathrm{n} \rightarrow \infty} \frac{1}{n} \sum_{i=1}^{n}\left(u_{i}-\bar{u}\right)\left(v_{i}-\bar{v}\right)
	\,, \quad \sigma_{u v} \text{ is called covariance}
\end{align}
$$

If 𝑢 and 𝑣 are not related to each other for measured physical quantities, 
the covariance would be zero.

So, the equation can be simplified to:
$$
\sigma_{X}^{2}=\sigma_{u}^{2}\left(\frac{\partial X}{\partial u}\right)_{\bar{u}}^{2}+\sigma_{v}^{2}\left(\frac{\partial X}{\partial v}\right)_{\bar{v}}^{2}
$$

利用上式，可以將以下四個例子計算出他們各自的誤差
![[https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/Error%20Analysis%20Notes/img/example.png]]
[(source)](https://chem.libretexts.org/Bookshelves/Analytical_Chemistry/Supplemental_Modules_(Analytical_Chemistry)/Quantifying_Nature/Significant_Digits/Propagation_of_Error)

可將此 $\sigma_{X}$ 值視為測得的平均值之精密度(或誤差)最佳估計。通常以$\bar{X} ± \sigma_{X}$表示某一物理量 x 的測量值。


## Example
$$
\frac{\Delta T}{T}(A, \tau)=A e^{-t / \tau}
$$在這裡我們設 $t=10 ps$
$$
\begin{aligned}
\mathrm{A} &= -1.92 \pm 0.07\left(\times 10^{-5}\right) \\
\tau &= 5.46 \pm 0.34 \quad
\end{aligned}
$$
$$
\begin{align}
\delta\left(\frac{\Delta T}{T}\right)
&=
  \sqrt{\left(\frac{\partial\left(\frac{\Delta T}{T}\right)}{\partial A} \delta A\right)^{2}+\left(\frac{\partial\left(\frac{\Delta T}{T}\right)}{\partial \tau} \delta \tau\right)^{2}}\\
\\[1.5ex]
&=
  \sqrt{\left(e^{-t / \tau} \times \delta A\right)^{2}+\left(A \frac{-t}{\tau^{2}} e^{-t / \tau} \times \delta \tau\right)^{2}}
\\[1.5ex]
&=
3.68 \times 10^{-7}\\
\end{align}
$$$$\frac{\Delta T}{T}(t=10)=3.07 \times 10^{-6} \pm 3.68 \times 10^{-7}$$
