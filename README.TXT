/**************************************************************************************************** 
*                             长按、单击、双击定义
* 长按事件：任何大于 KEY_LONG_PRESS_TIME 
* 单击事件：按下时间不超过 KEY_LONG_PRESS_TIME 且 释放后 KEY_WAIT_DOUBLE_TIME 内无再次按下的操作
* 双击事件：俩次短按时间间隔小于KEY_WAIT_DOUBLE_TIME，俩次短按操作合并为一次双击事件。
* 特殊说明：
*          1.短按和长按时间间隔小于 KEY_WAIT_DOUBLE_TIME，响应一次单击和长按事件，不响应双击事件
*          2.连续2n次短按，且时间间隔小于 KEY_WAIT_DOUBLE_TIME，响应为n次双击
*          3.连续2n+1次短按，且时间间隔小于 KEY_WAIT_DOUBLE_TIME，且最后一次KEY_WAIT_DOUBLE_TIME内无操作，
*				响应为n次双击 和 一次单击事件
****************************************************************************************************/

作者：nanshou
time：22.3.25

使用定时器，实现按键的长按、单击、双击
讲解博客：CSDN账户，"老子行李！"
教程参考链接：https://blog.csdn.net/qq_44078824/article/details/123757354

实验器材:
	自制开发板，STM32F03C8T6平台
	
实验目的:
	学习定时器中断、按键使用。实现单击双击长按操作
	
硬件资源:
	按键(PA0,也称WK_UP)
	定时器3
	串口1，用于打印输出
	
本程序只供学习使用，未经作者许可，不得用于其它任何用途