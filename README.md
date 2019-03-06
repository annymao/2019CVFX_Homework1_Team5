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

#### 1. Summer to winter 
<br>
<img src="./Images/summer2winter_1.png" width="400px" />
<img src="./Images/summer2winter_2.png" width="400px" />

#### 2. Winter to summer
<br>
<img src="./Images/winter2summer_1.png" width="400px" />
<img src="./Images/winter2summer_2.png" width="400px" />
<br>
<br>
由上面的結果可以看出來效果還不錯，已經有一點秋冬的感覺
接下來為 train 完 200 個 epoch 的結果 
<br>
<br>

#### 1. Summer to winter 
<br>
<img src="./Images/summer2winter_final1.png" width="400px" />
<img src="./Images/summer2winter_final2.png" width="400px" />
<img src="./Images/summer2winter_final3.png" width="400px" />
<img src="./Images/summer2winter_final4.png" width="400px" />

#### 2. Winter to summer
<br>
<img src="./Images/winter2summer_final1.png" width="400px" />
<img src="./Images/winter2summer_final2.png" width="400px" />
<img src="./Images/winter2summer_final3.png" width="400px" />
<br>
<br>

最後 train 完的結果我們認為更接近冬天一點，但感覺畫質有變差
