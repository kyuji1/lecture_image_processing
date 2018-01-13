# 課題4レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai4_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai4_1.jpg?raw=true)  
図1 グレースケール画像


図1の画像の濃度ヒストグラムを生成し表示する．

imhist(ORG); % ヒストグラムの表示

表示した結果を図2に示す．

![kadai4_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai4_2.jpg?raw=true)  
図2 濃度ヒストグラム

以上の結果から濃度ヒストグラムを生成することができることが分かった．この濃度ヒストグラムを用いることで画像の濃度変換や画像の2値化を行うことができる．
濃度ヒストグラムはどの濃度の画素で画像が構成されたかが分かるものであり，横軸が画素の濃度値，縦軸が画素の出現頻度を表している．今回の画像は0付近と250付近の濃度の画素が出現していないことや，130付近の濃度の画素が出現頻度が高いことが分かる．
