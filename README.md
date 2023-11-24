# 2023_2_open_202014969_project1

기본세팅
tensorflow 1.15.5 버전에 적합한 cuda10.0 다운로드
cuda10.0 버전에 적합한 cudnn7.4.2 다운로드
환경변수 시스템 변수 편집에 cudnn 추가 및 값에 큐다 디렉토리 연결

실행
conda create -n MaskRCNN python==3.7 //콘다에서 가상환경 MaskRCNN 파이썬 3.7 버전으로 생성
conda activate MaskRCNN //MaskRCNN 가상환경 실행
cd desktop //데스크탑으로 들어감
mkdir Mask_RCNN //Mask_RCNN 파일 생성
cd Mask_RCNN //Mask_RCNN 파일로 들어감
git clone https://github.com/matterport/Mask_RCNN //깃에있는 Mask_RCNN 코드를 클론해옴
pip install keras==2.1.2 //케라스 2.1.2 설치
pip install tensorflow-gpu==1.15.5 //텐서플로우 1.15.5 설치
python //파이썬 버전 확인 결과 3.7.0
import tensorflow as tf //텐서플로우 열기
ㄴTypeError: Descriptors cannot not be created directly (protoc >= 3.19.0) //프로토버프 버전과 텐서플로우 버전이 맞지않아서 발생
ㄴ해결 : pip install --upgrade protobuf==3.20.1 //프로토버프 버전을 3.20.1로 다운그레이드
print(tf.__version__) //텐서플로우 버전 확인 결과 1.15.5
import keras //케라스 열기
print(keras.__version__) //케라스 버전 확인 결과 2.1.2
cd Mask_RCNN //아까 클론한 Mask_RCNN 폴더로 들어감
mkdir model //모델 파일 생성
cd model //모델 파일 들어가기
mkdir balloon //발룬 파일 생성
cd balloon //발룬 파일 들어가기
mkdir datasets //데이터셋 파일 생성
*클론해온 Mask_RCNN파일에 mask_rcnn_balloon.h5, mask_rcnn_coco.h5 파일 다운로드 후 넣기
*datasets 파일에 다운로드해온 train, val 파일 넣기
pip install -U scikit-image==0.16.2 //서킷이미지 0.16.2 버전 설치
python balloon.py --dataset ../../model/balloon/datasets --weights ../../mask_rcnn_balloon.h5 --logs ../../model/balloon/logs --image ../../model/balloon/datasets/val/3800636873_ace2c2795f_b.jpg splash //이 명령어로 inference 실행

프로젝트 성공
