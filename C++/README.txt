�ļ��嵥
liveness.cpp�����������
liveness.h��������ͷ�ļ�
svm_model��ѵ��������svmģ��
svm_minmax������ʱ������һ���Ĳ���
./lbp��LBP������ȡ��
./libsvm-3.19��LibSVM��

��Ҫ������Ŀ��cpp�ļ���
liveness.cpp
./lbp/lbp.cpp
./lbp/histogram.cpp
./libsvm-3.19/svm.cpp
���õ�ͷ�ļ�Ϊ��
#include"liveness.h"

ʹ�õ�OpenCV�汾Ϊ3.0.0-RC1

ʹ�õ��������ݿ����NUAA, PRINT-ATTACK, CASIA
��Щ�ⲻ���������ճ�����

�������������
class ThuVisionFaceLiveCheck{
public:
	// Initialization: successful - true; failed - false
	bool Init();
	// Liveness Predict: input image path or Mat. 
	// If it is a real face, return true; otherwise, return false
	bool Check(std::string imgPath);
	bool Check(cv::Mat img);
private:
	int img_size;
	int LBP_size;
	svm_model* model;
	double* Feature_Max;
	double* Feature_Min;
	vector<int> mapping_r8;
	vector<int> mapping_r16;
};