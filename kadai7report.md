  # 課題7レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  
imhist(ORG); % 濃度ヒストグラムを生成、表示

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．またその画像の濃度ヒストグラムを図2に示す．

![kadai7_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai7_1.jpg?raw=true)  
図1 グレースケール画像

![kadai7_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai7_2.jpg?raw=true)  
図2 濃度ヒストグラム

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  

によって画素のダイナミックレンジを0~255に拡大する．

imagesc(ORG); colormap(gray); colorbar; % 画像の表示  
ORG = uint8(ORG); % 8ビットの符号なし整数に変換  
imhist(ORG); % 濃度ヒストグラムを生成、表示  

によってダイナミックレンジを拡大した画像を表示し，濃度ヒストグラムを生成する．
unit8を使用する理由はダイナミックレンジを拡大した時にORGを小数に変換したため，そのままではヒストグラムを生成することができない．そこでunit8を使い8ビットの符号なし整数に変換することでヒストグラムを生成することができるようになる．
表示した結果を図3，図4に示す．

![kadai7_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai7_3.jpg?raw=true)  
図3 ダイナミックレンジを拡大したグレースケール画像

![kadai7_4](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai7_4.jpg?raw=true)  
図4 ダイナミックレンジを拡大した濃度ヒストグラム

濃度ヒストグラムを比較するとダイナミックレンジの拡大前は濃度値が0の領域や255の領域が使われていなかったが，拡大後は使われていなかった領域にも使われるようになることが分かる．
ダイナミックレンジを拡大することでより広い濃度領域を使うことができ，より細かな濃度変化を表示できると考えられる．
