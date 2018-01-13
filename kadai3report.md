# 課題3レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai3_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai3_1.jpg?raw=true)  
図1 グレースケール画像


輝度値が64以上の画素を1，それ以外を0に変換して画像を表示する．

IMG = ORG > 64;  
imagesc(IMG); colormap(gray); colorbar;  

表示した結果を図2に示す．

![kadai3_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai3_2.jpg?raw=true)  
図2 輝度値64以上の画素を1としたとき


他の閾値で設定した結果を図3，図4，図5に示す．今回は輝度値がそれぞれ96以上，128以上，192以上の画素を1，それ以外を0に変換するよう設定した．

![kadai3_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai3_3.jpg?raw=true)  
図3 輝度値96以上の画素を1としたとき

![kadai3_4](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai3_4.jpg?raw=true)  
図4 輝度値128以上の画素を1としたとき

![kadai3_5](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai3_5.jpg?raw=true)  
図5 輝度値192以上の画素を1としたとき


以上の結果から，閾値を小さく設定した場合，大部分が白くなってしまい，逆に閾値を大きく設定した場合，大部分が黒くなってしまい画像を判別するのが非常に困難になることが分かった．
従って閾値処理を行う場合は，閾値をただ設定するのではなく画像に合う閾値を求め設定することが良いのではないかと考えられる．
