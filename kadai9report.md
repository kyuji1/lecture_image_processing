  # 課題9レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai9_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai9_1.jpg?raw=true)  
図1 グレースケール画像


ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

によって画像にノイズを添付する．表示した画像を図2に示す．

![kadai9_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai9_2.jpg?raw=true)  
図2 ノイズ添付画像

このノイズを添付した画像からフィルタを使用し，ノイズを除去する．

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタでノイズ除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

平滑化フィルタでノイズを除去した結果を図3に示す．

![kadai9_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai9_3.jpg?raw=true)  
図3 平滑フィルタでのノイズ除去結果

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタでノイズ除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

メディアンフィルタでノイズを除去した結果を図4に示す．

![kadai9_4](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai9_4.jpg?raw=true)  
図4 メディアンフィルタでのノイズ除去結果

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
IMG = filter2(f,IMG,'same'); % フィルタの適用  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

このフィルタは画像の濃度値の変化を強調して表現する高域強調フィルタである．結果を図5に示す．

![kadai9_5](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai9_5.jpg?raw=true)  
図5 高域強調フィルタでのノイズ除去結果

以上の結果から，平滑化フィルタは，周りの濃度値の平均値にするためノイズ部分はぼやけただけで完全には除去できていない．また対象物の輪郭もぼやけている．
メディアンフィルタは，周りの濃度値の中央値にするためノイズの濃度値がノイズの周りの濃度値に置き換えるため対象物の輪郭がぼやけることなくノイズが完全に除去できている．
高域強調フィルタは，画像の濃度値の変化を強調して表現するため，画像の濃度値の変化が判別しやすくなっている．
