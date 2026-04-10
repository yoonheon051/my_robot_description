# 🐊 my_robot_description

이 패키지는 **두산로보틱스 M0609** 로봇 팔과 **OnRobot RG2** 그리퍼를 통합하여 ROS 2 Humble 환경에서 시뮬레이션하기 위한 패키지입니다.

## 요구사항
ubuntu 22.04
ROS2 Humble

## 패키지 구성 요소 
**`urdf/`**: 로봇과 그리퍼의 결합 구조를 정의하는 Xacro 파일들이 포함되어 있습니다. 

**`meshes/`**: RViz 시각화를 위한 .stl 모델 파일들입니다. M0609와 RG2에 필수적인 파일만 남겨 최적화되었습니다.

**`launch/`**: `rviz_sim.launch.py`를 통해 로봇 상태 게시와 시각화를 한 번에 실행합니다. 

**`rviz/`**: `base_link` 고정 및 TF/RobotModel 자동 활성화 설정이 담긴 `default.rviz` 파일이 포함되어 있습니다. 

## 빌드 및 설치 방법 

### 의존성
* ROS2 Humble
* `robot_state_publisher`, `joint_state_publisher_gui`, `rviz2`, `gazebo_ros_pkgs`

```bash
# 워크스페이스 이동
cd ~/ros2_ws/src
git clone [https://github.com/yoonheon051/my_robot_description.git](https://github.com/yoonheon051/my_robot_description.git)

# 의존성 설치 및 빌드
cd ~/ros2_ws
rosdep install -i --from-path src --rosdistro $ROS_DISTRO -y
colcon build --packages-select my_robot_description
source install/setup.bash
