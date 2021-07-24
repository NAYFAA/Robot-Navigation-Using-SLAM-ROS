# Robot-Navigation-Using-SLAM-ROS
سوف اشرح المهمة الثانية في مسار الروبوت و الذكاء الصناعي في شركة الاساليب الذكية للتدريب الصيفي
حيث ان المطلوب استخدم
Use Turtlebot3 (ROS standard platform robot) with SLAM approach (simultaneous localization
and mapping)
لنشاء الخريطة و حفظها\
لذالك بدات بتثبيت الباكجات 
الخطوة الاولي - تثبيت باكج  Turtlebot3
sudo apt-get install ros-melodic-dynamixel-sdk
sudo apt-get install ros-melodic-turtlebot3-msgs
sudo apt-get install ros-melodic-turtlebot3
الخطوة الثانية- تثبيت باكج المحاكاةSimulation Package
cd ~/catkin_ws/src/
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
cd ~/catkin_ws && catkin_make
Then write cd or open new terminal and write source ~/catkin_ws/devel/setup.bash or use echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
هناك 3بيئات محاكاة معدة لـ
TurtleBot3
الخطوة الثالثة- نبدا ب
A-Empty world with a robot called "burger"
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch

B-TurtleBot3 World with a robot called "waffle"
export TURTLEBOT3_MODEL=waffle
roslaunch turtlebot3_gazebo turtlebot3_world.launch
C-TurtleBot3 House with a robot called waffle_pi
export TURTLEBOT3_MODEL=waffle_pi
roslaunch turtlebot3_gazebo turtlebot3_house.launch
و بامكاننا نختار واحدة للتحكم فيها و حفظها عن طريق لوحة الفاتيح بالكمبيوتر حيث ان
W: Forward, A: Left, S:Stop, D: Right, X:Backward.
عندما ننتهي من انشاء الخريطة نفتح تيرمنل جديد لحفظه
rosrun map_server map_saver -f ~/map
