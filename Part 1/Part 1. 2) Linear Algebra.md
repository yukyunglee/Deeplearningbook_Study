##### 진행자: 이유경 

<img src="C:\Users\yukyunglee\AppData\Roaming\Typora\typora-user-images\image-20200904150720323.png" alt="image-20200904150720323" style="zoom:50%;" />

### ISSUE

### 1) Broadcast

*Page : Deep Learning Book 34p*

형상이 다른 배열끼리 연산을 가능하게 해주는 기능을 **Broadcast**라 함

> We allow the addition of matrix and a vector, yielding another matrix

> : $C = A+b$     , where  $C_{i,j} + b_j$

> In other words, the vector b is added to each row of the matrix.

다음과 같은 설명이 존재할 때, 각 원소에 더해지는 값이 왜 j인가에 대해 논의함

결론적으로 broadcast를 할 때 column이 아니라 row를 더해주는 과정임을 알 수 있었다

( "the vector b is added to each row of the matrix" 라는 문구도 있음)

- 참고자료

  - 블로그 (https://sacko.tistory.com/16)

    <img src="C:\Users\yukyunglee\AppData\Roaming\Typora\typora-user-images\image-20200904150622847.png" alt="image-20200904150622847" style="zoom:70%;" />

  - 밑바닥부터 시작하는 딥러닝 1 (39p)

    ![image-20200904150646674](C:\Users\yukyunglee\AppData\Roaming\Typora\typora-user-images\image-20200904150646674.png)

### 2) Squared L2 Norm

*Page : Deep Learning Book 39p*

> The squared L2 norm is more convenient to work with mathematically and computationally than the L2 norm itself. For example, the derivatives of the squared L2 norm with respect to each element of x each depend only on the corresponding element of x, while all of the derivatives of the L2 norm depend on the entire vector. In many contexts, the squared L2 norm may be undesirable because it increases very slowly near the origin. In several machine learning applications, it is important to discriminate between elements that are exactly zero and elements that are small but nonzero

- 참고자료
  - **질문 : Why is the squared L2 norm sometimes preferred to the L2 norm in machine learning to measure distances?** (Quora : [링크](https://www.quora.com/Why-is-the-squared-L2-norm-sometimes-preferred-to-the-L2-norm-in-machine-learning-to-measure-distances))
  - **답변 :** To define a loss function both, the L2 norm and the squared L2 norm, provide the same optimization goal. But the squared L2 norm is computationally more simple, as you dont have to calculate the square root. ( 간단히 말하면 계산상으로 훨씬 수월해서 선호되는 경우도 있다고 합니다 !)

### 3) Eigen Value

고유값은 음수도 될 수 있음. 고유벡터가 변하지 않는것이고 (방향이 고정) 고유값을 통해 스케일링하면서 크기와 방향을 바꾸어줄 수 있음