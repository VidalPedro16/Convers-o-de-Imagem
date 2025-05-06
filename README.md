# Conversão de Imagem

1. Importar a biblioteca OpenCV
- Importa a biblioteca OpenCV, que é amplamente usada para processamento de imagens e visão computacional.

##

2. Ler a imagem
- Carrega a imagem chamada batman.jpg em formato de cor (RGB).
- A função cv2.imread() lê a imagem e a armazena como uma matriz NumPy.

##

3. Converter para escala de cinza
- Converte a imagem colorida em escala de cinza, usando a função cv2.cvtColor().
- O argumento cv2.COLOR_BGR2GRAY faz a conversão do modelo de cores BGR (utilizado pelo OpenCV) para tons de cinza.

##

4. Inverter as cores da imagem em tons de cinza
- Inverte os tons de cinza da imagem:
  * Pixels claros (valores próximos a 255) se tornam escuros (próximos a 0) e vice-versa.
- A função cv2.bitwise_not() realiza essa operação.

##

5. Aplicar desfoque gaussiano
- Aplica um desfoque gaussiano na imagem invertida.
  * (21, 21) é o tamanho do kernel (a área da vizinhança usada para o desfoque).
  * O 0 é o desvio padrão (sigma) calculado automaticamente.
- O desfoque suaviza a imagem, reduzindo detalhes finos e criando um efeito difuso.

##

6. Inverter o desfoque
- Inverte os tons de cinza da imagem desfocada.

##

7. Criar o efeito de esboço
- Divide pixel a pixel a imagem em tons de cinza original (grey_img) pela versão desfocada invertida (invertedblur).
  * O parâmetro scale=256.0 ajusta os valores de brilho.
- O resultado dessa divisão cria um efeito de desenho a lápis, enfatizando as bordas e detalhes mais claros da imagem original.

##

8. Salvar o resultado
- Salva o resultado final (sketch) como uma nova imagem chamada sketch.png.
