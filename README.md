# 🤖 my_robot_description

[cite_start]이 패키지는 **두산로보틱스 M0609** 로봇 팔과 **OnRobot RG2** 그리퍼를 통합하여 ROS 2 Humble 환경에서 시뮬레이션하기 위한 패키지입니다. [cite: 1, 16]

## 📌 프로젝트 개요
[cite_start]기존의 분산되어 있던 로봇과 그리퍼의 리소스를 하나로 통합하고, 실행 시마다 반복되는 설정을 자동화하여 개발 효율을 높였습니다. 

## [cite_start]📂 패키지 구성 요소 
* [cite_start]**`urdf/`**: 로봇과 그리퍼의 결합 구조를 정의하는 Xacro 파일들이 포함되어 있습니다. 
* **`meshes/`**: RViz 시각화를 위한 .stl 모델 파일들입니다. [cite_start]M0609와 RG2에 필수적인 파일만 남겨 최적화되었습니다. 
* [cite_start]**`launch/`**: `rviz_sim.launch.py`를 통해 로봇 상태 게시와 시각화를 한 번에 실행합니다. 
* [cite_start]**`rviz/`**: `base_link` 고정 및 TF/RobotModel 자동 활성화 설정이 담긴 `default.rviz` 파일이 포함되어 있습니다. 

## [cite_start]🛠️ 빌드 및 설치 방법 
워크스페이스(`cobot_ws`) 루트 디렉토리에서 아래 명령어를 실행하세요.

```bash
# 패키지 빌드
colcon build --symlink-install --packages-select my_robot_description

# 환경 변수 로드
source install/setup.bash