# 課題8レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai8_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai8_1.jpg?raw=true)  
図1 グレースケール画像


閾値128で二値化した画像を表示する．

IMG = ORG>128; % 閾値128で二値化 
imagesc(IMG); colormap(gray); colorbar;  axis image; % グレースケールにして画像表示

表示した結果を図2に示す．

![kadai8_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai8_2.jpg?raw=true)  
図2 二値化画像

二値化した画像にラベリングを行う．

IMG = bwlabeln(IMG);　%ラベリング
imagesc(IMG); colormap(jet); colorbar; % 画像の表示

表示した結果を図3に示す．

![kadai8_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai8_3.jpg?raw=true)  
図3 ラベリング結果

ラベリングを行うことによって二値化された画像の団塊図形を認識することができる．図3では色ごとに同じ連結成分に属する画素が分かるようになっている．
