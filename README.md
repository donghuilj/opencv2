# opencv2
1024实验室任务
import numpy as np
import cv2
from matplotlib import pyplot as plt
img=cv2.imread('zhaox.jpg',cv2.IMREAD_GRAYSCALE)
imgb = cv2.GaussianBlur(img,(5,5),0)
ret,thresh=cv2.threshold(imgb,127,255,cv2.THRESH_BINARY_INV)#+cv2.THRESH_OTSU)
imge,b,hierarchy = cv2.findContours(thresh,cv2.RETR_TREE,cv2.CHAIN_APPROX_NONE)
imga = cv2.drawContours(img,b,2, (0,0,255),2)
imgs=[imga,thresh]
for i in range(2):
    plt.subplot(1,2,i+1)
    plt.imshow(imgs[i],'gray')
#plt.imshow(thresh,'gray')
plt.show()
