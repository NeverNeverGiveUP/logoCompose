# logoCompose
一个关于logo识别的项目
#include<opencv2\opencv.hpp>
using namespace cv;
using namespace std;
int main()
{
	Mat imag, result, imag1;
	imag1 = imread("2.png", 1);
	imag = imread("2.png", 0);    //将读入的彩色图像直接以灰度图像读入  
	namedWindow("原图", 1);
	imshow("原图",imag1);
	imshow("灰度图图", imag);
	result = imag.clone();
	//进行二值化处理，选择30，200.0为阈值  
	threshold(imag, result, 100, 255, CV_THRESH_BINARY);
	namedWindow("二值化图像");
	imshow("二值化图像", result);
	waitKey();
	return 0;
}
