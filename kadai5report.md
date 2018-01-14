# 課題5レポート
「Girl」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Girl.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai5_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai5_1.jpg?raw=true)  
図1 グレースケール画像


判別分析法を用いて画像を二値化した画像を表示する．

C1 = H(1:i); %ヒストグラムを2つのクラスに分ける

C2 = H(i+1:256);

n1 = sum(C1); %画素数を算出する

n2 = sum(C2);

myu1 = mean(C1); %画素の平均値を算出する

myu2 = mean(C2);

sigma1 = var(C1); %分散の算出をする

sigma2 = var(C2);

sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散を算出する

sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散を算出する

if max_val<sigma_B/sigma_w %sigma_B/sigma_wが最大とする閾値max_thresを求める

max_val = sigma_B/sigma_w; 

max_thres =i;

で求めた閾値が求まる．

IMG = ORG > max_thres;

imagesc(IMG); colormap(gray); colorbar;

で求めた閾値で二値化した画像を表示した結果を図2に示す．

![kadai5_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai5_2.jpg?raw=true)  
図2 判別分析法による二値画像

判別分析法を用いると背景と対象物がそれぞれまとまっており，また対象物が判別できるように背景との違いが際立つようになることが分かった．
