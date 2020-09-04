##### 진행자: 이유경 



<img src="C:\Users\yukyunglee\AppData\Roaming\Typora\typora-user-images\image-20200904152004102.png" alt="image-20200904152004102" style="zoom:80%;" />

### [9/4: ~7.5까지 진행]

#### Topic 1: 모델 selection 관점에서 bias, Variance 

*(출처: 강필성 교수님 Business Analytics 수업)*

<img src="C:\Users\yukyunglee\AppData\Roaming\Typora\typora-user-images\image-20200904151711316.png" alt="image-20200904151711316" style="zoom:50%;" />

이건 7.1에서 나오는 bias와 variance는 NN관점에서 regularization에 사용하는것들을 의미함. 두가지 관점이 어떻게 다른지 함께 토론함



#### Topic 2 : Data augmentation

 Adversarial training과 augmentation에 대해 다루었던 @서승완박사과정 연구실 세미나의 토론 주제에대해 다시 한번 생각하는 시간을 가졌음 ! [세미나 링크](http://dsba.korea.ac.kr/seminar/?uid=1323&amp;mod=document&amp;pageid=1)

* 정규화 관점에서는 Adversarial training을 data augmentation으로 볼수있다는 의견에 동의! 

> Injecting noise in the input to a neural network (Sietsma and Dow, 1991)
>
> can also be seen as a form of data augmentation.



#### Topic 3 : Label smoothing

*(출처 : https://3months.tistory.com/465)*

Pytorch에서 쓸수 있어요 !  [ [link](https://medium.com/towards-artificial-intelligence/how-to-use-label-smoothing-for-regularization-aa349f7f1dbb) ]

one-hot으로 인코딩된 label vector에 uniform distribution을 결합한것

(K = Class갯수, alpha = 하이퍼 파라미터)
$$
y_{label smoothing} = (1-\alpha) * y_{one hot} +\alpha/K
$$

- 데이셋을 구성할때 mislabeling은 항상 일어날 수 있는 문제임
- binary classificaion을 예시로 했을때, label은 0 혹은 1로 주어지는 상황이 있다고 가정해보자!
- 이때 label이 1이라는것은 이 데이터의 레이블이 1이라는것을 100% 확신한다는 의미
- 하지만 mislabeling이 일어날 수 있기때문에 100% 확신하면 error가 생기게됨 (잘못된 학습)
- label을 0 혹은 1이 아니라, smoothing된 값으로 부여하는것이 Label smoothing임 !
- **결국 이러한 과정을 거치면 모델의 일반화 성능이 높아지기때문에, 이는 regularization이라 볼 수 있음 !!!**
- 예를들어 0,1이었던 label을 → 0.1, 0.9로 만들게되면 loss를 산출할 때 0.9의 신뢰도로 label을 학습하기때문에 model이 overconfident해지는 경향을 막아주게 된다고 함