# Training-for-Competition
### Team
* 윤소미, 장주찬, 전규원, 한정현, 허 권
### Project
* Kaggle Competition : HuBMAP + HPA = Hacking The Human Body
### Introduction
#### Train Codes and files for Competition
* Modle : Efficient Unet
1. Encoder : b0 -b7
2. 모델과 데이터셋을 고정한 후, encoder부분을 바꿔가며 학습
3. 일부로 Overfit을 준 후, 하나씩 규제를 걸어가며 진행
4. 제출 점수가 가장 좋았던 encoder 고정
5. 고정된 encoder에 가장 어울리는 이미지의 input size 찾은 후 데이터 핸들링
6. 다양한 test image size를 고려해 multi scale 데이터셋 제작 > 성능이 가장 잘 나옴
7. 동일한 encoder model에서 input size 256, 512로 다르게 학습시킨 model ensemble
8. Inference 에서 encoder model ensemble 추가
9. best score : 0.77
* Model : ResNeSt
1. Encoder : resnest101, resnest200, resnest269
2. Efficient Unet과의 모델 앙상블을 위해 학습
3. Efficient Unet에서 가장 학습이 좋았던 데이터셋을 고정
4. best score : 0.78
### Result
* dataset : convert256 reduce4,6,12 stride128 dataset / convert512 reduce2,3,6 stride256 dataset
* models : Efficient-Unet encoder b1, b3, b5 / ResNeSt 101, 200, 269
* method : ensemble
* Kaggle score : Public - 0.78 / Private - 0.76 (final result)
<img width="571" alt="kaggle competiton score" src="https://user-images.githubusercontent.com/106142393/192099762-6f3a314b-3e14-4eb3-bc17-f4dd6c125d38.PNG">   

* rank : 124 / 1245 teams (90th percentile)
<img width="416" alt="kaggle score" src="https://user-images.githubusercontent.com/106142393/192099824-e2266a51-37b1-4150-a80e-72a7a5554a7f.PNG">

*  **Bronze Medal**
### Env and Requirements
* Google Colab, VScode, AWS
* Pytorch, Fastai, Weights and Bias, cv2, sklearn, lovasz
### Reference
* https://www.kaggle.com/code/befunny/hubmap-fast-ai-starter-efficientnet
* https://www.kaggle.com/code/shuheiakahane/inference-hubmap-fast-ai-starter-efficientnet
