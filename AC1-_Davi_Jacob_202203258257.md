# Diferenças entre Áreas da Computação Visual

## 1) Síntese de Imagens (Computação Gráfica)

**Explicação**  
A Computação Gráfica é a área que lida com a criação de imagens do zero a partir de dados e instruções, como modelos 3D, coordenadas ou equações matemáticas. O objetivo é "desenhar" digitalmente, gerando uma imagem que não existia antes. Pense em como os filmes de animação ou os videogames são feitos: tudo é criado sinteticamente.

**Exemplo**  
Este código simples usa a biblioteca Pillow para criar uma imagem totalmente nova e desenhar um retângulo azul e uma elipse verde nela.

```python
from PIL import Image, ImageDraw
import matplotlib.pyplot as plt

# Cria uma imagem em branco com 200x200 pixels
img = Image.new('RGB', (200, 200), 'white')
draw = ImageDraw.Draw(img)

# Desenha um retângulo azul
draw.rectangle([(50, 50), (150, 150)], fill='blue')

# Desenha uma elipse verde
draw.ellipse([(20, 20), (80, 80)], fill='green')

# Mostra a imagem gerada
plt.imshow(img)
plt.title("Imagem Sintetizada")
plt.axis('off')
plt.show()

print("Imagem gerada com sucesso!")
```

---

## 2) Processamento de Imagens

**Explicação**  
O Processamento de Imagens é a manipulação de imagens que já existem para melhorar sua qualidade ou prepará-las para alguma tarefa. A entrada e a saída são sempre imagens.

**Exemplo**  
Neste exemplo, usamos a biblioteca OpenCV para aplicar um filtro de desfoque em uma imagem.

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Cria uma imagem simples de exemplo (um quadrado branco em fundo preto)
img_original = np.zeros((150, 150, 3), dtype=np.uint8)
cv2.rectangle(img_original, (40, 40), (110, 110), (255, 255, 255), -1)
img_original = cv2.cvtColor(img_original, cv2.COLOR_BGR2RGB)

# Aplica um filtro de desfoque gaussiano
img_desfocada = cv2.GaussianBlur(img_original, (15, 15), 0)

# Mostra a imagem original e a processada para comparação
fig, axs = plt.subplots(1, 2, figsize=(8, 4))
axs[0].imshow(img_original)
axs[0].set_title('Original')
axs[0].axis('off')

axs[1].imshow(img_desfocada)
axs[1].set_title('Processada (Desfoque)')
axs[1].axis('off')
plt.show()

print("Imagens salvas com sucesso!")
```

---

## 3) Visão Computacional (Visão Artificial)

**Explicação**  
A Visão Computacional vai além do processamento: ela ensina o computador a "entender" e "interpretar" o que está na imagem. O objetivo é extrair informações de alto nível, como identificar objetos, rostos ou contar coisas.

**Exemplo**  
Este código simples, usando NumPy, demonstra a ideia de contar o número de objetos.

```python
import numpy as np

# Cria uma imagem de exemplo (representada como um array 2D)
# 1s representam o fundo e 0s representam os objetos
img_objetos = np.array([
    [1, 1, 0, 1, 1],
    [1, 0, 0, 0, 1],
    [1, 1, 0, 1, 1],
    [1, 1, 1, 1, 1]
])

# Conta quantos objetos (pixels com valor 0) existem na "imagem"
num_objetos = np.sum(img_objetos == 0)

print("A imagem tem", num_objetos, "objetos.")
```

---

## 4) Visualização Computacional

**Explicação**  
A Visualização Computacional traduz dados abstratos (como números e estatísticas) em algo visual e fácil de entender, como gráficos e diagramas.

**Exemplo**  
Com matplotlib, este código transforma dados de vendas em um gráfico de barras.

```python
import matplotlib.pyplot as plt

# Dados de vendas de exemplo
meses = ['Jan', 'Fev', 'Mar', 'Abr', 'Mai', 'Jun']
vendas = [120, 150, 180, 90, 200, 170]

# Cria o gráfico de barras
plt.figure(figsize=(8, 5))
plt.bar(meses, vendas, color='skyblue')

# Títulos e rótulos
plt.title('Vendas Mensais (Primeiro Semestre)')
plt.xlabel('Mês')
plt.ylabel('Total de Vendas')
plt.show()

print("Gráfico de vendas gerado!")
```

---
