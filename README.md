# Meta-Pseudo-Labels

# Background

**Meta Learning** - ****“학습하는 방법을 학습한다.”

“Learning new concepts and skills fast **with a few training examples”**

Learning into two stages : 

- The “learner” model, **trained for operating a given task**
- A optimizer learns **how** **to update the learner model’s parameters**

---

# Approches

## Pseudo Label

- Noisy Student  Model의 핵심 아이디어

1. Labeled data를 사용해 Teacher 학습

2. 학습한 Teacher로 unlabeled data를 추론하여 pseudo label 생성

3. Labeled data와 pseudo label data 결합

4. 결합한 데이터셋으로 Student 학습

결과적으로, 보다 풍부한 데이터와 augmentation 덕분에 더 좋은 성능을 가진 Student Model이 만들어짐

![https://blog.kakaocdn.net/dn/bSio2g/btrpvSb5Ukc/oUYs3I4gqF0qt6jMBNDklk/img.png](https://blog.kakaocdn.net/dn/bSio2g/btrpvSb5Ukc/oUYs3I4gqF0qt6jMBNDklk/img.png)

- 기존 pseudo label 단점
    - Teacher가 부정확한 경우 → Pseudo label 부정확 → Student는 잘못된 Pseudo label을 학습
    - 확증 편향(confirmation bias) 발생

---

# MPL(Meta Pseudo Labels)

## 확증편향 보완

- **Feedback** from the Student → Teacher to generate better pseudo labels
- Student 학습 과정에서 Teacher도 지속적으로 업데이트
    - Teacher가 더 좋은 pseudo label을 생성할 수 있도록, Teacher가 지속적으로 조정됨
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c76590ad-eebf-4b7f-82fe-7348e69aeb9b/Untitled.png)
    

## Semi-Supervised Learning

- Teacher Network → Unlabeled data에서 Pseudo Label 생성
- Student Network → Unlabeled data에서 Pseudo Label로 학습

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e1c46aa-d398-4760-9af3-7b973afc3be1/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3cf78e5a-e6db-40e3-83a7-b115bf02f0b4/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bc340c20-30e4-46e5-8c9f-474b08c24b85/Untitled.png)

---

## Reference

[](https://arxiv.org/pdf/2003.10580v4.pdf)

[Meta Pseudo Labels](https://medium.com/@nainaakash012/meta-pseudo-labels-6480acb1b68)

[Meta-Learning: Learning to Learn Fast](https://lilianweng.github.io/posts/2018-11-30-meta-learning/)

[Have A Nice AI](https://kmhana.tistory.com/33)
