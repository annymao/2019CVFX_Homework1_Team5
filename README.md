# 2019CVFX_Homework1_Team5

## Training

### 1. apple2orange
<img src="./Images/training_a2o.png" width="600px" />

### 2. horse2zebra
<img src="./Images/training_h2z.png" width="600px" />

### 3. summer2winter
<img src="./Images/training_s2w.png" width="600px" />


## Inference Personal Images(CYCLE GAN)
### Winter2Summer Dataset
由於 GAN 在訓練時不一定會越 train 越好，有可能是中間的結果是最佳的，<br>
所以我們在 train 的時候也不定時會 inference 觀察產生的結果
以下為 train 到 124 個 epoch 的結果 <br>
<img src="./Images/summer2winter_1.png" width="400px" />
<img src="./Images/summer2winter_2.png" width="400px" />
<br>
<img src="./Images/winter2summer_1.png" width="400px" />
<img src="./Images/winter2summer_2.png" width="400px" />
<br>
由上面的結果可以看出來效果還不錯，夏天轉冬天的部分已經有秋冬的感覺。第二張圖片可以看到，原本湖邊綠地的部分被換成了很像積雪的感覺，而冬天轉夏天的圖片葉子也看得出變得翠綠。但是目前的缺點是照片看起來都偏紅色系。
<br>
接下來為 train 完 200 個 epoch 的結果 
<br>
<img src="./Images/summer2winter_final1.png" width="400px" />
<img src="./Images/summer2winter_final2.png" width="400px" />
<br>
<img src="./Images/summer2winter_final3.png" width="400px" />
<img src="./Images/summer2winter_final4.png" width="400px" />
<br>
<img src="./Images/winter2summer_final1.png" width="400px" />
<img src="./Images/winter2summer_final2.png" width="400px" />
<br>
<img src="./Images/winter2summer_final3.png" width="400px" />
<br>

最後 train 完的結果我們認為更接近冬天一點，畫面也不會像 124 個 epoch 的時候一樣會偏紅色，轉換出來的圖片更有冬天的滄桑感。而在冬天轉夏天的部分綠色的深淺效果好像也有更明顯。

### Orange2apple
橘子與蘋果互換的部分效果不如夏天冬天轉換的效果好，我們認為這是因為蘋果跟橘子要轉換是需要比較局部的顏色以及材質轉移（橘子的皮會有一種特殊的紋路），而冬天夏天要達到效果的話，如果整體色調上有轉移成功就可以讓人有冬/夏天的感覺了。<br>
<img src="./Images/apple2orange.png" width="400px" />
<img src="./Images/apple2orange_2.png" width="400px" />
<br>

### horse2zebra
馬跟斑馬的互換，一開始我們認為蠻成功的 <br>
<img src="./Images/h2z_1.png" width="400px" />
<img src="./Images/h2z_2.png" width="400px" />
<br>
直到我們試到下面這個有趣的失敗的例子<br>
<img src="./Images/horse2zebra.png" width="400px" />
<br>
我們認為會導致這樣的結果是因為人的皮膚也會偏黃色或咖啡色，導致再 training 的時候，可能還沒訓練到能夠分辨出人與馬的差異，所以在轉換的時候會把人也裹上斑馬紋。

### monet2photo



## Compare With Other Methods
其他方法方面，我們嘗試了助教提供的super fast color transfer，以下是轉換後的結果。<br>
<img src="./Images/ctbi_d2n.png" width="400px" />
<img src="./Images/ctbi_orange.png" width="400px" />
<img src="./Images/ctbi_s2w.png" width="400px" />
<img src="./Images/ctbi_w2s.png" width="400px" />
<img src="./Images/s2w_failed1.png" width="400px" />
<br>
相較於需要超過 24 小時 training 的 cycleGAN，super fast color transfer 只要透過對 source 跟 target 兩張圖片的 L*a*b channels 的 mean 與 standard deviation 計算做轉換，在運算上快速許多。然而，由上面的成果圖片可以觀察到，super fast color transfer 的效果比較像直接將 target 圖片套上有 source 圖片顏色的濾鏡，並且可能會轉出奇怪的圖片（如上最後一張圖）。很明顯地，cycleGAN 在細節的處理上較為精緻（例如，夏天的藍天空會轉換成灰冷的顏色，綠葉變得比較暗沈或楓紅)。此外，cycleGAN只需要一張圖片即可轉換，super fast color transfer則需要一張source圖片（轉換色調）以及target圖片（要被轉換色調的圖）才能完成。同時，使用super fast color transfer的方法，如果兩張照片大小不同也能順利轉換。
<br>

