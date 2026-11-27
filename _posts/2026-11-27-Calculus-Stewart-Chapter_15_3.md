---
title: Stewart Calculus - 15.3 Double Integrals in Polar Coordinates
description: 극좌표에서의 이중적분
author: MRC2407
date: 2026-11-27
categories: [Blogging]
tags: [Text Review, mathematics, calculus]

hidden: false
---

Stewart의 Calculus: Early Transcendentals 9판의 15.3절, 'Double Integrals in Polar Coordinates'를 읽어보자.

영역 $$R$$이 중심이 원점인 원판일 때 이중적분 $$\iint_R f(x,y)\,dA$$의 값을 구하고자 한다고 하자. 이 경우 직교좌표를 사용하여 $$R$$을 나타내는 것은 상당히 복잡하지만, 극좌표를 사용하면 $$R$$을 쉽게 나타낼 수 있다. 일반적으로 $$R$$이 극좌표를 사용하여 더 쉽게 나타낼 수 있는 영역이라면, 먼저 극좌표로 변환하여 이중적분의 값을 구하는 것이 유리한 경우가 많다.

#### 극좌표의 복습

극좌표는 10.3절에서 도입하였다. 그림 1에서 한 점의 극좌표 $$(r,\theta)$$와 그 점의 직교좌표 $$(x,y)$$는 다음 방정식들에 의해 서로 관련되어 있다는 것을 상기하라.

$$
r^2=x^2+y^2
\qquad
x=r\cos\theta
\qquad
y=r\sin\theta
$$

중심이 원점인 원의 방정식은 극좌표에서 특히 간단하다. 단위원의 방정식은 $$r=1$$이며, 이 원으로 둘러싸인 영역은 그림 2(a)에 나타나 있다. 그림 2(b)는 극좌표로 편리하게 나타낼 수 있는 또 다른 영역을 보여 준다.

극좌표로 적절하게 나타낼 수 있는 다른 일반적인 곡선들에 대해서는 표 10.3.1을 복습하는 것이 좋다.

#### 극좌표에서의 이중적분

그림 2의 영역들은 그림 3에 나타난 극직사각형(polar rectangle)

$$
R=\{(r,\theta)\mid
a\leq r\leq b,\ \alpha\leq\theta\leq\beta\}
$$

의 특별한 경우이다. $$R$$이 극직사각형일 때 이중적분 $$\iint_R f(x,y)\,dA$$를 계산하기 위해, 구간 $$[a,b]$$를 폭이 $$\Delta r=(b-a)/m$$으로 일정한 $$m$$개의 소구간 $$[r_{i-1},r_i]$$로 나누고, 구간 $$[\alpha,\beta]$$를 폭이 $$\Delta\theta=(\beta-\alpha)/n$$으로 일정한 $$n$$개의 소구간 $$[\theta_{j-1},\theta_j]$$로 나눈다. 그러면 원 $$r=r_i$$와 반직선 $$\theta=\theta_j$$는 극직사각형 $$R$$을 그림 4에 나타난 작은 극직사각형 $$R_{ij}$$들로 나눈다.

> 그림 4를 그림 15.1.3과 비교하라.

작은 극직사각형

$$
R_{ij}=\{(r,\theta)\mid
r_{i-1}\leq r\leq r_i,
\theta_{j-1}\leq\theta\leq\theta_j\}
$$

의 '중심'은 다음과 같은 극좌표를 갖는다.

$$
r_i^*=\frac12(r_{i-1}+r_i)
\qquad
\theta_j^*=\frac12(\theta_{j-1}+\theta_j)
$$

반지름이 $$r$$이고 중심각이 $$\theta$$인 원의 부채꼴의 넓이가 $$\frac12r^2\theta$$라는 사실을 이용하여 $$R_{ij}$$의 넓이를 계산한다. 각각의 중심각이 $$\Delta\theta=\theta_j-\theta_{j-1}$$인 두 부채꼴의 넓이를 서로 빼면 $$R_{ij}$$의 넓이는 다음과 같다.

$$
\begin{aligned}
\Delta A_i
&=\frac12r_i^2\Delta\theta
-\frac12r_{i-1}^2\Delta\theta\\
&=\frac12(r_i^2-r_{i-1}^2)\Delta\theta\\
&=\frac12(r_i+r_{i-1})(r_i-r_{i-1})\Delta\theta\\
&=r_i^*\Delta r\Delta\theta
\end{aligned}
$$

우리는 일반적인 직사각형을 사용하여 이중적분 $$\iint_R f(x,y)\,dA$$를 정의하였지만, 연속함수 $$f$$에 대해서는 극직사각형을 사용하더라도 항상 같은 답을 얻는다는 것을 보일 수 있다. $$R_{ij}$$의 중심의 직교좌표는 $$(r_i^*\cos\theta_j^*,r_i^*\sin\theta_j^*)$$이므로, 전형적인 리만 합은 다음과 같다.

$$
\begin{aligned}
&\sum_{i=1}^{m}\sum_{j=1}^{n}
f(r_i^*\cos\theta_j^*,r_i^*\sin\theta_j^*)\Delta A_i\\
&=\sum_{i=1}^{m}\sum_{j=1}^{n}
f(r_i^*\cos\theta_j^*,r_i^*\sin\theta_j^*)
r_i^*\Delta r\Delta\theta
\end{aligned}
\tag{1}
$$

$$g(r,\theta)=rf(r\cos\theta,r\sin\theta)$$라고 쓰면 식 (1)의 리만 합은 다음과 같이 나타낼 수 있다.

$$
\sum_{i=1}^{m}\sum_{j=1}^{n}
g(r_i^*,\theta_j^*)\Delta r\Delta\theta
$$

이것은 다음 이중적분에 대한 리만 합이다.

$$
\int_\alpha^\beta\int_a^b
g(r,\theta)\,dr\,d\theta
$$

따라서 다음을 얻는다.

$$
\begin{aligned}
&\iint_R f(x,y)\,dA\\
&=\lim_{m,n\to\infty}
\sum_{i=1}^{m}\sum_{j=1}^{n}
f(r_i^*\cos\theta_j^*,r_i^*\sin\theta_j^*)\Delta A_i\\
&=\lim_{m,n\to\infty}
\sum_{i=1}^{m}\sum_{j=1}^{n}
g(r_i^*,\theta_j^*)\Delta r\Delta\theta\\
&=\int_\alpha^\beta\int_a^b
g(r,\theta)\,dr\,d\theta\\
&=\int_\alpha^\beta\int_a^b
f(r\cos\theta,r\sin\theta)r\,dr\,d\theta
\end{aligned}
$$

**2. 이중적분에서 극좌표로의 변환(Change to Polar Coordinates in a Double Integral)**

함수 $$f$$가 다음과 같이 주어지는 극직사각형 $$R$$에서 연속이고

$$
0\leq a\leq r\leq b,\qquad
\alpha\leq\theta\leq\beta
$$

여기서 $$0\leq\beta-\alpha\leq2\pi$$이면,

$$
\iint_R f(x,y)\,dA
=
\int_\alpha^\beta\int_a^b
f(r\cos\theta,r\sin\theta)r\,dr\,d\theta
$$

이다.

공식 (2)는 이중적분에서 직교좌표를 극좌표로 변환하려면 $$x=r\cos\theta$$와 $$y=r\sin\theta$$로 쓰고, $$r$$과 $$\theta$$에 대한 적절한 적분한계를 사용하며, $$dA$$를 $$r\,dr\,d\theta$$로 대체하면 된다는 것을 말해 준다. 공식 (2)의 우변에 있는 추가적인 인자 $$r$$을 잊지 않도록 주의하라. 이를 기억하는 고전적인 방법이 그림 5에 나타나 있는데, 여기서 '무한소' 극직사각형은 변의 길이가 $$r\,d\theta$$와 $$dr$$인 일반적인 직사각형으로 생각할 수 있으며, 따라서 그 '넓이'는 $$dA=r\,dr\,d\theta$$이다.

**예제 1**

다음 이중적분의 값을 구하여라.

$$
\iint_R(3x+4y^2)\,dA
$$

여기서 $$R$$은 위쪽 반평면에서 원 $$x^2+y^2=1$$과 $$x^2+y^2=4$$로 둘러싸인 영역이다.

**풀이**

영역 $$R$$은 다음과 같이 나타낼 수 있다.

$$
R=\{(x,y)\mid
y\geq0,\ 1\leq x^2+y^2\leq4\}
$$

이 영역은 그림 2(b)에 나타난 반고리이며, 극좌표에서는 $$1\leq r\leq2$$, $$0\leq\theta\leq\pi$$로 주어진다. 따라서 공식 (2)에 의해

$$
\begin{aligned}
&\iint_R(3x+4y^2)\,dA\\
&=\int_0^\pi\int_1^2
[3(r\cos\theta)+4(r\sin\theta)^2]r\,dr\,d\theta\\
&=\int_0^\pi\int_1^2
(3r^2\cos\theta+4r^3\sin^2\theta)\,dr\,d\theta\\
&=\int_0^\pi
[r^3\cos\theta+r^4\sin^2\theta]_{r=1}^{r=2}
\,d\theta\\
&=\int_0^\pi(7\cos\theta+15\sin^2\theta)\,d\theta\\
&=\int_0^\pi
\left[7\cos\theta+\frac{15}{2}(1-\cos2\theta)\right]
d\theta\\
&=\left[
7\sin\theta+\frac{15\theta}{2}
-\frac{15}{4}\sin2\theta
\right]_0^\pi\\
&=\frac{15\pi}{2}
\end{aligned}
$$

이다.

> 여기에서는 삼각함수의 항등식
>
> $$\sin^2\theta=\frac12(1-\cos2\theta)$$
>
> 를 사용하였다. 삼각함수의 적분에 관한 지침은 7.2절을 참조하라.

**예제 2**

다음 이중적분의 값을 구하여라.

$$
\int_{-1}^{1}\int_0^{\sqrt{1-x^2}}
(x^2+y^2)\,dy\,dx
$$

**풀이**

이 반복적분은 그림 6에 나타나 있으며 다음과 같이 주어지는 영역 $$R$$에서의 이중적분이다.

$$
R=\{(x,y)\mid
-1\leq x\leq1,\ 0\leq y\leq\sqrt{1-x^2}\}
$$

이 영역은 반원판이므로 극좌표를 사용하면 더 간단하게 나타낼 수 있다.

$$
R=\{(r,\theta)\mid
0\leq\theta\leq\pi,\ 0\leq r\leq1\}
$$

따라서 다음을 얻는다.

$$
\begin{aligned}
&\int_{-1}^{1}\int_0^{\sqrt{1-x^2}}
(x^2+y^2)\,dy\,dx\\
&=\int_0^\pi\int_0^1(r^2)r\,dr\,d\theta\\
&=\int_0^\pi
\left[\frac{r^4}{4}\right]_{r=0}^{r=1}d\theta\\
&=\frac14\int_0^\pi d\theta\\
&=\frac{\pi}{4}
\end{aligned}
$$

**예제 3**

평면 $$z=0$$과 포물면 $$z=1-x^2-y^2$$으로 둘러싸인 입체의 부피를 구하여라.

**풀이**

포물면의 방정식에 $$z=0$$을 대입하면 $$x^2+y^2=1$$을 얻는다. 이것은 평면이 포물면과 원 $$x^2+y^2=1$$에서 교차한다는 것을 의미하므로, 입체는 포물면의 아래쪽에 있고 $$x^2+y^2\leq1$$로 주어지는 원판 $$D$$의 위쪽에 놓여 있다[그림 7과 그림 2(a)를 참조하라]. 극좌표에서 $$D$$는 $$0\leq r\leq1$$, $$0\leq\theta\leq2\pi$$로 주어진다. $$1-x^2-y^2=1-r^2$$이므로 부피는

$$
\begin{aligned}
V&=\iint_D(1-x^2-y^2)\,dA\\
&=\int_0^{2\pi}\int_0^1(1-r^2)r\,dr\,d\theta\\
&=\int_0^{2\pi}d\theta
\int_0^1(r-r^3)\,dr\\
&=2\pi\left[\frac{r^2}{2}-\frac{r^4}{4}\right]_0^1\\
&=\frac{\pi}{2}
\end{aligned}
$$

이다.

예제 3에서 극좌표 대신 직교좌표를 사용하였다면 다음을 얻었을 것이다.

$$
\begin{aligned}
V&=\iint_D(1-x^2-y^2)\,dA\\
&=\int_{-1}^{1}
\int_{-\sqrt{1-x^2}}^{\sqrt{1-x^2}}
(1-x^2-y^2)\,dy\,dx
\end{aligned}
$$

이것은 $$\int(1-x^2)^{3/2}\,dx$$를 구하는 과정을 포함하므로 계산하기 쉽지 않다.

지금까지 우리가 수행한 과정은 그림 8에 나타난 더 복잡한 유형의 영역으로 확장할 수 있다. 이것은 15.2절에서 고려했던 직교좌표에서의 제Ⅱ형 영역과 유사하다. 실제로 이 절의 공식 (2)와 공식 15.2.4를 결합하면 다음 공식을 얻는다.

함수 $$f$$가 다음과 같은 형태의 극좌표 영역에서 연속이면,

$$
D=\{(r,\theta)\mid
\alpha\leq\theta\leq\beta,
h_1(\theta)\leq r\leq h_2(\theta)\}
$$

다음이 성립한다.

$$
\iint_D f(x,y)\,dA
=
\int_\alpha^\beta
\int_{h_1(\theta)}^{h_2(\theta)}
f(r\cos\theta,r\sin\theta)r\,dr\,d\theta
\tag{3}
$$

특히 이 공식에서 $$f(x,y)=1$$, $$h_1(\theta)=0$$, $$h_2(\theta)=h(\theta)$$로 놓으면, $$\theta=\alpha$$, $$\theta=\beta$$, $$r=h(\theta)$$로 둘러싸인 영역 $$D$$의 넓이는

$$
\begin{aligned}
A(D)&=\iint_D1\,dA\\
&=\int_\alpha^\beta\int_0^{h(\theta)}
r\,dr\,d\theta\\
&=\int_\alpha^\beta
\left[\frac{r^2}{2}\right]_0^{h(\theta)}d\theta\\
&=\int_\alpha^\beta
\frac12[h(\theta)]^2\,d\theta
\end{aligned}
$$

임을 알 수 있으며, 이것은 공식 10.4.3과 일치한다.

**예제 4**

이중적분을 사용하여 네 잎 장미곡선 $$r=\cos2\theta$$의 한 꽃잎으로 둘러싸인 영역의 넓이를 구하여라.

**풀이**

그림 9에 나타난 곡선의 개형으로부터 하나의 꽃잎은 다음 영역으로 주어진다는 것을 알 수 있다.

$$
D=\left\{(r,\theta)\mid
-\frac{\pi}{4}\leq\theta\leq\frac{\pi}{4},
0\leq r\leq\cos2\theta
\right\}
$$

따라서 넓이는

$$
\begin{aligned}
A(D)&=\iint_D dA\\
&=\int_{-\pi/4}^{\pi/4}
\int_0^{\cos2\theta}r\,dr\,d\theta\\
&=\int_{-\pi/4}^{\pi/4}
\left[\frac12r^2\right]_0^{\cos2\theta}d\theta\\
&=\frac12\int_{-\pi/4}^{\pi/4}
\cos^22\theta\,d\theta\\
&=\frac14\int_{-\pi/4}^{\pi/4}
(1+\cos4\theta)\,d\theta\\
&=\frac14\left[
\theta+\frac14\sin4\theta
\right]_{-\pi/4}^{\pi/4}\\
&=\frac{\pi}{8}
\end{aligned}
$$

이다.

**예제 5**

포물면 $$z=x^2+y^2$$의 아래쪽에 있고, $$xy$$평면의 위쪽에 있으며, 원기둥 $$x^2+y^2=2x$$의 내부에 있는 입체의 부피를 구하여라.

**풀이**

입체는 경계인 원의 방정식이 $$x^2+y^2=2x$$로 주어지는 원판 $$D$$의 위쪽에 놓여 있다. 또는 완전제곱식을 만들면

$$
(x-1)^2+y^2=1
$$

이다. (그림 10과 그림 11을 참조하라.)

극좌표에서는 $$x^2+y^2=r^2$$이고 $$x=r\cos\theta$$이므로, 경계인 원 $$x^2+y^2=2x$$는 $$r^2=2r\cos\theta$$, 즉 $$r=2\cos\theta$$가 된다. 따라서 원판 $$D$$는 다음과 같이 주어진다.

$$
D=\left\{(r,\theta)\mid
-\frac{\pi}{2}\leq\theta\leq\frac{\pi}{2},
0\leq r\leq2\cos\theta
\right\}
$$

그리고 공식 (3)에 의해 다음을 얻는다.

$$
\begin{aligned}
V&=\iint_D(x^2+y^2)\,dA\\
&=\int_{-\pi/2}^{\pi/2}
\int_0^{2\cos\theta}r^2r\,dr\,d\theta\\
&=\int_{-\pi/2}^{\pi/2}
\left[\frac{r^4}{4}\right]_0^{2\cos\theta}d\theta\\
&=4\int_{-\pi/2}^{\pi/2}\cos^4\theta\,d\theta\\
&=8\int_0^{\pi/2}\cos^4\theta\,d\theta\\
&=8\int_0^{\pi/2}
\left(\frac{1+\cos2\theta}{2}\right)^2d\theta\\
&=2\int_0^{\pi/2}
\left[
1+2\cos2\theta+\frac12(1+\cos4\theta)
\right]d\theta\\
&=2\left[
\frac32\theta+\sin2\theta+\frac18\sin4\theta
\right]_0^{\pi/2}\\
&=2\left(\frac32\cdot\frac{\pi}{2}\right)\\
&=\frac{3\pi}{2}
\end{aligned}
$$

#### 15.3 연습문제

**1–6.** 영역 $$R$$이 그림에 나타나 있다. 극좌표와 직교좌표 중 어느 것을 사용할지 결정하고, $$\iint_R f(x,y)\,dA$$를 반복적분으로 나타내어라. 여기서 $$f$$는 $$R$$에서의 임의의 연속함수이다.

**1–6.** (원문의 그림 생략)

**7–8.** 주어진 적분으로 넓이가 표현되는 영역을 그리고 적분의 값을 구하여라.

**7.**

$$
\int_{\pi/4}^{3\pi/4}\int_1^2
r\,dr\,d\theta
$$

**8.**

$$
\int_{\pi/2}^{\pi}\int_0^{2\sin\theta}
r\,dr\,d\theta
$$

**9–16.** 극좌표로 변환하여 주어진 적분의 값을 구하여라.

**9.**

$$
\iint_D x^2y\,dA
$$

여기서 $$D$$는 중심이 원점이고 반지름이 5인 원판의 위쪽 절반이다.

**10.**

$$
\iint_R(2x-y)\,dA
$$

여기서 $$R$$은 원 $$x^2+y^2=4$$와 직선 $$x=0$$ 및 $$y=x$$로 둘러싸인 제1사분면의 영역이다.

**11.**

$$
\iint_R\sin(x^2+y^2)\,dA
$$

여기서 $$R$$은 중심이 원점이고 반지름이 각각 1과 3인 두 원 사이에 있는 제1사분면의 영역이다.

**12.**

$$
\iint_R\frac{y^2}{x^2+y^2}\,dA
$$

여기서 $$R$$은 원 $$x^2+y^2=a^2$$과 $$x^2+y^2=b^2$$ 사이에 있는 영역이며, $$0<a<b$$이다.

**13.**

$$
\iint_D e^{-x^2-y^2}\,dA
$$

여기서 $$D$$는 반원 $$x=\sqrt{4-y^2}$$과 $$y$$축으로 둘러싸인 영역이다.

**14.**

$$
\iint_D\cos\sqrt{x^2+y^2}\,dA
$$

여기서 $$D$$는 중심이 원점이고 반지름이 2인 원판이다.

**15.**

$$
\iint_R\arctan(y/x)\,dA
$$

여기서

$$
R=\{(x,y)\mid
1\leq x^2+y^2\leq4,\ 0\leq y\leq x\}
$$

이다.

**16.**

$$
\iint_D x\,dA
$$

여기서 $$D$$는 원 $$x^2+y^2=4$$와 $$x^2+y^2=2x$$ 사이에 있는 제1사분면의 영역이다.

**17–22.** 이중적분을 사용하여 영역 $$D$$의 넓이를 구하여라.

**17.** (원문의 그림 생략)

$$
r=1-\cos\theta,\qquad r=1+\cos\theta
$$

**18.** (원문의 그림 생략)

$$
r=\sqrt{\theta}
$$

**19.** (원문의 그림 생략)

$$
r=\sin\theta,\qquad r=\cos\theta
$$

**20.** (원문의 그림 생략)

$$
r=\frac{1}{\sqrt2},\qquad r^2=\cos2\theta
$$

**21.** $$D$$는 제1사분면에 있는 장미곡선 $$r=\sin3\theta$$의 한 꽃잎이다.

**22.** $$D$$는 원 $$(x-1)^2+y^2=1$$의 내부에 있고 원 $$x^2+y^2=1$$의 외부에 있는 영역이다.

**23–24.**

(a) 곡면의 아래쪽에 있고 영역 $$D$$의 위쪽에 있는 입체의 부피에 대한 극좌표에서의 반복적분을 설정하여라.

(b) 반복적분의 값을 계산하여 입체의 부피를 구하여라.

**23.** (원문의 그림 생략)

$$
z=1+xy
$$

**24.** (원문의 그림 생략)

$$
z=x^2+y^2
$$

**25–28.**

(a) 주어진 함수의 그래프 아래쪽에 있고 영역 $$D$$의 위쪽에 있는 입체의 부피에 대한 극좌표에서의 반복적분을 설정하여라.

(b) 반복적분의 값을 계산하여 입체의 부피를 구하여라.

**25.** $$f(x,y)=y$$

**26.** $$f(x,y)=xy^2$$

**27.** $$f(x,y)=x$$

**28.** $$f(x,y)=1$$

(원문의 그림 생략)

**29–37.** 극좌표를 사용하여 주어진 입체의 부피를 구하여라.

**29.** 포물면 $$z=x^2+y^2$$의 아래쪽에 있고 원판 $$x^2+y^2\leq25$$의 위쪽에 있는 입체

**30.** 원뿔면 $$z=\sqrt{x^2+y^2}$$의 아래쪽에 있고 고리 모양의 영역 $$1\leq x^2+y^2\leq4$$의 위쪽에 있는 입체

**31.** 평면 $$2x+y+z=4$$의 아래쪽에 있고 원판 $$x^2+y^2\leq1$$의 위쪽에 있는 입체

**32.** 구면 $$x^2+y^2+z^2=16$$의 내부에 있고 원기둥 $$x^2+y^2=4$$의 외부에 있는 입체

**33.** 반지름이 $$a$$인 구

**34.** 포물면 $$z=1+2x^2+2y^2$$과 평면 $$z=7$$로 둘러싸인 제1팔분공간의 입체

**35.** 원뿔면 $$z=\sqrt{x^2+y^2}$$의 위쪽에 있고 구면 $$x^2+y^2+z^2=1$$의 아래쪽에 있는 입체

**36.** 두 포물면 $$z=6-x^2-y^2$$과 $$z=2x^2+2y^2$$으로 둘러싸인 입체

**37.** 원기둥 $$x^2+y^2=4$$와 타원면 $$4x^2+4y^2+z^2=64$$ 모두의 내부에 있는 입체

**38.** (a) 반지름이 $$r_1$$인 원기둥 모양의 드릴을 사용하여 반지름이 $$r_2$$인 구의 중심을 관통하는 구멍을 뚫는다. 남아 있는 고리 모양의 입체의 부피를 구하여라.

(b) (a)에서 구한 부피를 고리의 높이 $$h$$에 관한 식으로 나타내어라. 부피는 $$r_1$$이나 $$r_2$$가 아니라 오직 $$h$$에만 의존한다는 점에 주목하라.

**39–42.** 극좌표로 변환하여 반복적분의 값을 구하여라.

**39.**

$$
\int_0^2\int_0^{\sqrt{4-x^2}}
e^{-x^2-y^2}\,dy\,dx
$$

**40.**

$$
\int_0^a
\int_{-\sqrt{a^2-y^2}}^{\sqrt{a^2-y^2}}
(2x+y)\,dx\,dy
$$

**41.**

$$
\int_0^{1/2}
\int_{\sqrt3y}^{\sqrt{1-y^2}}
xy^2\,dx\,dy
$$

**42.**

$$
\int_0^2\int_0^{\sqrt{2x-x^2}}
\sqrt{x^2+y^2}\,dy\,dx
$$

**43–44.** 이중적분을 $$r$$에 관한 하나의 일중적분으로 나타내어라. 그런 다음 계산기(또는 컴퓨터)를 사용하여 적분값을 소수점 이하 넷째 자리까지 정확하게 구하여라.

**43.**

$$
\iint_D e^{(x^2+y^2)^2}\,dA
$$

여기서 $$D$$는 중심이 원점이고 반지름이 1인 원판이다.

**44.**

$$
\iint_D xy\sqrt{1+x^2+y^2}\,dA
$$

여기서 $$D$$는 원판 $$x^2+y^2\leq1$$의 제1사분면에 놓인 부분이다.

**45.** 수영장은 지름이 10 m인 원형이다. 깊이는 동서 방향의 직선들을 따라 일정하며, 남쪽 끝에서의 1 m부터 북쪽 끝에서의 2 m까지 선형적으로 증가한다. 수영장에 있는 물의 부피를 구하여라.

**46.** 농업용 스프링클러가 반지름이 50 m인 원형 영역에 물을 뿌린다. 스프링클러에서 $$r$$ m 떨어진 곳에 시간당 $$e^{-r}$$ m의 깊이만큼 물을 공급한다.

(a) $$0<R\leq50$$이면, 스프링클러를 중심으로 하는 반지름 $$R$$인 원의 내부 영역에 시간당 공급되는 물의 총량은 얼마인가?

(b) 반지름이 $$R$$인 원의 내부 영역에 시간당 단위 제곱미터당 공급되는 물의 평균량을 나타내는 식을 구하여라.

**47.** 고리 모양의 영역 $$a^2\leq x^2+y^2\leq b^2$$에서 함수

$$
f(x,y)=\frac{1}{\sqrt{x^2+y^2}}
$$

의 평균값을 구하여라. 여기서 $$0<a<b$$이다.

**48.** $$D$$를 중심이 원점이고 반지름이 $$a$$인 원판이라고 하자. $$D$$에 있는 점들에서 원점까지의 평균 거리는 얼마인가?

**49.** 극좌표를 사용하여 다음 합을 하나의 이중적분으로 결합하여라.

$$
\begin{aligned}
&\int_{1/\sqrt2}^{1}
\int_{\sqrt{1-x^2}}^x xy\,dy\,dx\\
&+\int_1^{\sqrt2}\int_0^x xy\,dy\,dx\\
&+\int_{\sqrt2}^2\int_0^{\sqrt{4-x^2}}
xy\,dy\,dx
\end{aligned}
$$

그런 다음 이중적분의 값을 구하여라.

**50.** (a) 전체 평면 $$\mathbb R^2$$에서의 이상적분을 다음과 같이 정의한다.

$$
\begin{aligned}
I&=\iint_{\mathbb R^2}e^{-(x^2+y^2)}\,dA\\
&=\int_{-\infty}^{\infty}
\int_{-\infty}^{\infty}
e^{-(x^2+y^2)}\,dy\,dx\\
&=\lim_{a\to\infty}
\iint_{D_a}e^{-(x^2+y^2)}\,dA
\end{aligned}
$$

여기서 $$D_a$$는 반지름이 $$a$$이고 중심이 원점인 원판이다. 다음이 성립함을 보여라.

$$
\int_{-\infty}^{\infty}
\int_{-\infty}^{\infty}
e^{-(x^2+y^2)}\,dA=\pi
$$

(b) (a)에 있는 이상적분의 동등한 정의는 다음과 같다.

$$
\iint_{\mathbb R^2}e^{-(x^2+y^2)}\,dA
=\lim_{a\to\infty}
\iint_{S_a}e^{-(x^2+y^2)}\,dA
$$

여기서 $$S_a$$는 꼭짓점이 $$(\pm a,\pm a)$$인 정사각형이다. 이를 사용하여 다음이 성립함을 보여라.

$$
\int_{-\infty}^{\infty}e^{-x^2}\,dx
\int_{-\infty}^{\infty}e^{-y^2}\,dy
=\pi
$$

(c) 다음을 유도하여라.

$$
\int_{-\infty}^{\infty}e^{-x^2}\,dx
=\sqrt{\pi}
$$

(d) 변수변환 $$t=\sqrt2x$$를 수행하여 다음이 성립함을 보여라.

$$
\int_{-\infty}^{\infty}e^{-x^2/2}\,dx
=\sqrt{2\pi}
$$

(이것은 확률과 통계학의 기본적인 결과이다.)

**51.** 연습문제 50(c)의 결과를 사용하여 다음 적분의 값을 구하여라.

(a)

$$
\int_0^\infty x^2e^{-x^2}\,dx
$$

(b)

$$
\int_0^\infty\sqrt{x}e^{-x}\,dx
$$
