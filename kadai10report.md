# 課題10レポート
「Mandrill」を原画像とする．この画像は高さ150ピクセル，幅150ピクセルである．

ORG=imread('Mandrill.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールに変換  
imagesc(ORG); axis image; % 画像の表示  

によって原画像を読み込み、グレースケールにして表示した結果を図1に示す．

![kadai10_1](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai10_1.jpg?raw=true)  
図1 グレースケール画像

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

プレウィット法でエッジ抽出を行った結果を図2に示す．

![kadai10_2](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai10_2.jpg?raw=true)  
図2 プレウィット法によるエッジ抽出

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示

ソベル法でエッジ抽出を行った結果を図3に示す．

![kadai10_3](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai10_3.jpg?raw=true)  
図3 ソベル法によるエッジ抽出

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示


キャニー法でエッジ抽出を行った結果を図4に示す．

![kadai10_4](https://github.com/kyuji1/lecture_image_processing/blob/master/figure/kadai10_4.jpg?raw=true)  
図3 キャニー法によるエッジ抽出

以上の結果から，プレウィット法とソベル法ではあまり違いがみられなかったがキャニー法は多くのエッジを抽出することができていることが分かる．
