# 課題6レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai6_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai6_1.jpg?raw=true)  
図1 グレースケール画像


閾値128で二値化した画像を表示する．

IMG = ORG>128; % 128による二値化 
imagesc(IMG); colormap(gray); colorbar;  axis image; % グレースケールにして画像表示

表示した結果を図2に示す．

![kadai6_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai6_2.jpg?raw=true)  
図2 閾値128で二値化した画像

ディザ法によって二値化した画像を表示する．

IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % グレースケールにして画像表示

![kadai6_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai6_3.jpg?raw=true)  
図3 ディザ法によって二値化した画像

閾値を決め二値化する方法よりディザ法を使って画像を表示した方が，画像の濃淡をより複雑に表すことができることが分かった．
