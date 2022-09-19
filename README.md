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
* Model : ResNeSt101

### Env and Requirements
* Google Colab, VScode, AWS
* Pytorch, Fastai, Weights and Bias, cv2, sklearn, lovasz
### Reference
* https://www.kaggle.com/code/befunny/hubmap-fast-ai-starter-efficientnet
* https://www.kaggle.com/code/shuheiakahane/inference-hubmap-fast-ai-starter-efficientnet
