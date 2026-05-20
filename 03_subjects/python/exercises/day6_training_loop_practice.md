# Day 6 Training Loop Practice

## 적용 학습법

- 기본: 파인만 역할 반전
- 보조: 빈칸 코드

## 목표

PyTorch 훈련 루프의 5단계를 말과 코드로 설명한다.

## 훈련 루프 5단계

1. forward
2. loss 계산
3. gradient 초기화
4. backward
5. optimizer step

## 빈칸 코드

```python
for epoch in range(3):
    pred = model(x_train)
    loss = loss_fn(pred, y_train)

    ___.zero_grad()
    ___.backward()
    ___.step()

    print(epoch, loss.item())
```

질문:

1. `zero_grad()`를 하지 않으면 어떤 문제가 생기는가?
2. `backward()`와 `step()`의 역할 차이는 무엇인가?
3. 이 루프를 초등학생에게 설명하듯 말해라.
