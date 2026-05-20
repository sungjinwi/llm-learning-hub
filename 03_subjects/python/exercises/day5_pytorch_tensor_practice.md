# Day 5 PyTorch Tensor Practice

## 적용 학습법

- 기본: 코드와 수식 1:1 매핑
- 보조: 출력 예측

## 목표

Tensor shape, reshape, autograd의 감각을 만든다.

## 실습 1 - shape 예측

```python
import torch

x = torch.tensor([[1.0, 2.0], [3.0, 4.0]])
y = x.reshape(4, 1)

print(x.shape)
print(y.shape)
```

## 실습 2 - autograd

```python
import torch

w = torch.tensor(2.0, requires_grad=True)
loss = (w - 5) ** 2
loss.backward()

print(w.grad)
```

질문:

1. loss는 어떤 함수인가?
2. w가 2일 때 기울기는 얼마인가?
3. `requires_grad=True`가 없으면 어떤 일이 생기는가?
