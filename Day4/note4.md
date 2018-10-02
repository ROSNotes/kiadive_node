# 机器人视觉OpenCV
## 图片
* 导入图片:img = cv2.imbed('image.jpg')
* 显示图片:cv2.imshow("Display",img),其中Display为显示图片的windows窗口名称
* 图片生存时间：cv2.waitKey(0),0表示按任意键关闭
## 视频
```
import numpy as np
import cv2

cap = cv2.VideoCapture(2)

while(True):
  ret,frame = cap.read()
  gray = cv2.cvtColor(frame,cv2.COLOR_BGR2GRAY) #图片灰度化
  img 90 = np.rot90(frame) #画面旋转90度
  cv2.imshow('frame',frame)
  if cv2.waitKey(1)& 0xFF == ord('q'):
     break

cap.release()
cv2.destroyAllWindows() 
```

## 图片画线
```
img = cv2.imread('/home/intel/Desktop/image.jpeg')
line = cv2.line(img,(0,255),(511,255),(0,255,0),25) #在图片上按指定的坐标画线
cv2.imshow('draw_line',line)
```

# 消息发布
```
import rospy
from std_msgs.msg import String

def talker():
   pub = rospy.Publisher('chatter',String,queue_size=10)#创建话题
   rospy.init_node('talker',anonymous=True)#创建节点
   rate = rospy.Rate(10)#发布消息的频率
   
   while not rospy.is_shutdown():
        hello_str = "hello world %s" % rospy.get_time()
        rospy.loginfo(hello_str)#在终端上输出
        pub.publish(hello_str)
        rate.sleep()

if __name__ == '__main__':
   try:
       talker()
   except rospy.ROSInterruptException:#捕获异常
       pass
```

## 通过python控制小乌龟
```
import rospy
from geometry_msgs.msg import Twist

pub = rospy.Publisher('/turtle1/cmd_vel',Twist,queue_size=10)#给小乌龟的话题发消息
rospy.init_node('xhxwg')
xg_rate = rospy.Rate(5)

while not rospy.is_shutdown():
   movecmd = Twist()
   movecmd.linear.x = 2 #设置线速度
   movecmd.angular.z = 2 #设置角速度

   pub.publish(movecmd)
   xg_rate.sleep()
```

## 消息订阅
```
import rospy
from std_msgs.msg import String
from geometry_msgs.msg import Twist

def callback(data): #当小乌龟运动线速度大于0，小乌龟必然在运动
	if(data.linear.x>0 ):
		rospy.loginfo("dongl") #在终端上显示小乌龟的运动情况
	rospy.loginfo(data.linear.x)

def listener():
	rospy.init_node('listener',anonymous=True)
	rospy.Subscriber("/turtle1/cmd_vel",Twist,callback)#订阅话题
	rospy.spin()

if __name__ == '__main__':
	listener()
```
