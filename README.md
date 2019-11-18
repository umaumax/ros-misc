# ros misc

## print ros time
```
pip3 install --user rospkg
pip3 install --user PyYaml
```

```
#!/usr/bin/env python3

import rospy

def main():
    rospy.init_node('rostime')
    now = rospy.get_rostime()
    rospy.loginfo("Current time %i %i", now.secs, now.nsecs)

if __name__ == '__main__':
    main()
```

## rosbag-to-image.launch
* NOTE
  * you must mkdir output dir
  * you must use abs path
  * you can use launch file any working directory

```
roslaunch ./rosbag-to-image.launch rosbag:=<abs path of rosbag> image_topic:=/xxx/yyy output_dir:=<abs path of dir> filename_format:="frame%04d.png"
```

* FYI
  * [rosbag から連番の画像ファイルを生成する \- Yura YuLife]( http://yura2.hateblo.jp/entry/2017/06/20/rosbag_%E3%81%8B%E3%82%89%E9%80%A3%E7%95%AA%E3%81%AE%E7%94%BB%E5%83%8F%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E7%94%9F%E6%88%90%E3%81%99%E3%82%8B )
  * [roslaunch/XML \- ROS Wiki]( http://wiki.ros.org/roslaunch/XML )
    * launchファイルのいじり方がわかる
