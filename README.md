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
* Model : ResNeSt
1. Encoder : resnest101, resnest200
2. Efficient Unet과의 모델 앙상블을 위해 학습
3. Efficient Unet에서 가장 학습이 좋았던 데이터셋을 고정

### Env and Requirements
* Google Colab, VScode, AWS
* Pytorch, Fastai, Weights and Bias, cv2, sklearn, lovasz
### Reference
* https://www.kaggle.com/code/befunny/hubmap-fast-ai-starter-efficientnet
* https://www.kaggle.com/code/shuheiakahane/inference-hubmap-fast-ai-starter-efficientnet
