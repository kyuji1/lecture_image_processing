# 課題2レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai2_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai2_1.jpg?raw=true)  
図1 グレースケール画像


階調数を2階調に設定して画像を表示する．

IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;

表示した結果を図2に示す．

![kadai2_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai2_2.jpg?raw=true)  
図2 2階調


4階調と8階調に設定したときの画像を表示する．今回はどちらも量子化間隔を等しくして量子化を行った．結果を図3，図4に示す．

![kadai2_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai2_3.jpg?raw=true)  
図3 4階調

![kadai2_4](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai2_4.jpg?raw=true)  
図4 8階調


以上の結果から階調数が少ないと濃度変化が十分に表現できないことが分かる．また，量子化間隔が粗い場合，画像に疑似的に輪郭が存在しているようにみえる疑似輪郭と呼ばれる現象が起こった．
