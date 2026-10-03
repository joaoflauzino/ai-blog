---
title: 'Entendendo o Gradient Descent e Otimização em Redes Neurais'
description: 'Uma introdução matemática e prática ao algoritmo fundamental de treinamento de modelos de Machine Learning e Deep Learning.'
pubDate: '2026-10-03'
---

O **Gradiente Descendente** (ou *Gradient Descent*) é a espinha dorsal da maior parte dos algoritmos modernos de Machine Learning e Deep Learning. Seja treinando uma simples regressão linear ou um Large Language Model (LLM) com bilhões de parâmetros, a essência do processo de otimização se baseia em encontrar o mínimo de uma função de perda (Loss Function).

---

## 1. A Matemática do Gradiente Descendente

Considere uma função de custo parametrizada por um vetor de pesos $\theta \in \mathbb{R}^d$, que mede o erro do modelo em relação aos dados observados:

$$
J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} \left( h_\theta(x^{(i)}) - y^{(i)} \right)^2
$$

Onde:
- $m$ é a quantidade de exemplos de treino.
- $h_\theta(x)$ é a predição da hipótese.
- $y$ é o valor real (ground truth).

Para minimizar $J(\theta)$, atualizamos iterativamente os parâmetros na direção oposta ao vetor gradiente $\nabla J(\theta)$:

$$
\theta_{t+1} = \theta_t - \alpha \nabla J(\theta_t)
$$

Aqui, $\alpha > 0$ representa a **taxa de aprendizado** (*learning rate*). Se $\alpha$ for muito pequeno, a convergência será lenta; se for muito grande, o algoritmo pode divergir.

---

## 2. Implementação Prática em Python (com PyTorch)

Abaixo temos uma implementação elegante demonstrando a convergência com **PyTorch**:

```python
import torch

# Dados sintéticos: y = 3x + 2 + ruído
torch.manual_seed(42)
x = torch.randn(100, 1)
y = 3 * x + 2 + 0.1 * torch.randn(100, 1)

# Parâmetros com gradiente habilitado
w = torch.randn(1, requires_grad=True)
b = torch.zeros(1, requires_grad=True)

learning_rate = 0.05
epochs = 100

for epoch in range(epochs):
    # Forward pass: predição e Mean Squared Error (MSE)
    y_pred = x * w + b
    loss = torch.mean((y_pred - y) ** 2)

    # Backward pass: cálculo automático dos gradientes
    loss.backward()

    # Atualização dos pesos (sem rastrear operações no grafo computacional)
    with torch.no_grad():
        w -= learning_rate * w.grad
        b -= learning_rate * b.grad

        # Zera os gradientes acumulados para a próxima iteração
        w.grad.zero_()
        b.grad.zero_()

    if (epoch + 1) % 20 == 0:
        print(f"Epoch [{epoch+1}/{epochs}] - Loss: {loss.item():.4f} - w: {w.item():.3f}, b: {b.item():.3f}")
```

---

## 3. Principais Variantes

Na prática com grandes volumes de dados (Big Data e LLMs), o cálculo do gradiente sobre todo o conjunto de dados (Batch Gradient Descent) se torna proibitivamente custoso. Por isso, utilizamos variantes:

1. **Stochastic Gradient Descent (SGD)**: Atualiza $\theta$ a cada amostra individual.
2. **Mini-batch SGD**: Divide os dados em lotes (ex: 32, 64, 128 amostras), equilibrando estabilidade e eficiência de GPU.
3. **Otimizadores com Momento e Adaptativos**: Como **Adam**, **AdamW** e **RMSprop**, que utilizam médias móveis dos gradientes passados para acelerar a convergência.

---

## Conclusão

Compreender o cálculo diferencial e a geometria da superfície de perda é o primeiro passo para dominar a arquitetura de modelos avançados. Nos próximos artigos, vamos explorar como o **AdamW** ajusta a taxa de decaimento de peso (*weight decay*) e por que ele é a escolha padrão para o pré-treinamento de Transformers!
