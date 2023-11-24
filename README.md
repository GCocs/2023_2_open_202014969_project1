# 2023_2_open_202014969_project1
<br/>
기본세팅<br/>
tensorflow 1.15.5 버전에 적합한 cuda10.0 다운로드<br/>
cuda10.0 버전에 적합한 cudnn7.4.2 다운로드<br/>
환경변수 시스템 변수 편집에 cudnn 추가 및 값에 큐다 디렉토리 연결<br/>
<br/>
실행<br/>
conda create -n MaskRCNN python==3.7 //콘다에서 가상환경 MaskRCNN 파이썬 3.7 버전으로 생성<br/>
conda activate MaskRCNN //MaskRCNN 가상환경 실행<br/>
cd desktop //데스크탑으로 들어감<br/>
mkdir Mask_RCNN //Mask_RCNN 파일 생성<br/>
cd Mask_RCNN //Mask_RCNN 파일로 들어감<br/>
git clone https://github.com/matterport/Mask_RCNN //깃에있는 Mask_RCNN 코드를 클론해옴<br/>
pip install keras==2.1.2 //케라스 2.1.2 설치<br/>
pip install tensorflow-gpu==1.15.5 //텐서플로우 1.15.5 설치<br/>
python //파이썬 버전 확인 결과 3.7.0<br/>
import tensorflow as tf //텐서플로우 열기<br/>
ㄴTypeError: Descriptors cannot not be created directly (protoc >= 3.19.0) //프로토버프 버전과 텐서플로우 버전이 맞지않아서 발생<br/>
ㄴ해결 : pip install --upgrade protobuf==3.20.1 //프로토버프 버전을 3.20.1로 다운그레이드<br/>
print(tf.__version__) //텐서플로우 버전 확인 결과 1.15.5<br/>
import keras //케라스 열기<br/>
print(keras.__version__) //케라스 버전 확인 결과 2.1.2<br/>
cd Mask_RCNN //아까 클론한 Mask_RCNN 폴더로 들어감<br/>
mkdir model //모델 파일 생성<br/>
cd model //모델 파일 들어가기<br/>
mkdir balloon //발룬 파일 생성<br/>
cd balloon //발룬 파일 들어가기<br/>
mkdir datasets //데이터셋 파일 생성<br/>
<br/>
*클론해온 Mask_RCNN파일에 mask_rcnn_balloon.h5, mask_rcnn_coco.h5 파일 다운로드 후 넣기<br/>
https://github.com/matterport/Mask_RCNN/releases/download/v2.1/mask_rcnn_balloon.h5<br/>
https://github.com/matterport/Mask_RCNN/releases/download/v1.0/mask_rcnn_coco.h5<br/>
<br/>
*datasets 파일에 다운로드해온 train, val 파일 넣기<br/>
https://github.com/matterport/Mask_RCNN/releases/download/v2.1/balloon_dataset.zip<br/>
<br/>
pip install -U scikit-image==0.16.2 //서킷이미지 0.16.2 버전 설치<br/>
cd samples/balloon //클론해온 Mask_RCNN 폴더의 샘플 폴더안에있는 발룬폴더 들어가기<br/>
python balloon.py --dataset ../../model/balloon/datasets --weights ../../mask_rcnn_balloon.h5 --logs ../../model/balloon/logs --image ../../model/balloon/datasets/val/3800636873_ace2c2795f_b.jpg splash //이 명령어로 inference 실행<br/>
<br/>
프로젝트 성공
