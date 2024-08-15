import cv2
import numpy as np
# colorir o 'AS' em heatmap

h = 720 #altura
w = 1270 #largura

imagem = np.ones([h,w],dtype=np.uint8) #cria a imagem em branco
texto = 'AS'

#tentei pegar algo meio centralizado ..
x = int(w/4)
y = int(h*3/4)

# Escala do texto
escala = 15 
cor = (255, 0, 0)  # Azul
espessura = 60
imagem = cv2.putText(imagem, texto, (x, y), cv2.FONT_HERSHEY_SIMPLEX, escala, cor, espessura)

for i in range(0, 256, 5):

    cor = (i, 0, 255 - i)
    
    imagem_copy = imagem.copy() 
    imagem_copy = cv2.putText(imagem_copy, texto, (x, y), cv2.FONT_HERSHEY_SIMPLEX, escala, cor, espessura)
    
    #  o mapa de calor 
    heatMap = cv2.applyColorMap(imagem_copy, cv2.COLORMAP_JET)
    
    cv2.imshow('Imagem com Texto Colorido', heatMap)
    cv2.waitKey(100) #para acelerar , esse valor <100
