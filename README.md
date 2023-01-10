#include <iostream>
#define _USE_MATH_DEFINES
#include<math.h>
using namespace std;

class Box
{
	double width; //幅
	double heigth; //高さ
	double depth; //奥行

    public: Box(double width, double heigth, double depth)
    {
	   this->width = width;
	   this->heigth = heigth;
	   this->depth = depth;
    } 
    public: double GetSurface()//表面積
    {
	   return width * heigth * depth;
    } 
    public: double GetVolume()//体積
    {
	   return (width * heigth + heigth * depth + depth * width) * 2; 
    }
};
class Cylinder 
{
	double bottom; //底面の半径
	double heigth; //高さ

    public: Cylinder(double bottom, double heigth)
	{
		this->bottom = bottom;
		this->heigth = heigth;	  
	}
    public: double GetSurface()//表面積
    {
		return bottom * 2.0f * M_PI * heigth + bottom * bottom * M_PI * 2.0f;
	}
    public: double GetVolume()//体積
    {
		return bottom * bottom * M_PI * heigth;
	}
};
class Cone 
{
	double bottom; //底面の半径
	double heigth; //高さ

    public: Cone(double bottom, double heigth) 
	{
		this->bottom = bottom;
		this->heigth = heigth;
	}
    public: double GetSurface()//表面積
    {
	    return M_PI * bottom * (sqrt(bottom * bottom + heigth * heigth) + bottom);
    }
    public: double GetVolume()//体積
    {
	    return bottom * bottom * M_PI * heigth / 3.0f;
    }
};
class Sphere 
{
	double bottom; //底面の半径

    public: Sphere(double bottom) 
    {
	    this->bottom = bottom;
    }
    public: double GetSurface()//表面積
    {
	    return M_PI * bottom * bottom * 4.0f;
    }
    public: double GetVolume()//体積
    {
	    return bottom * bottom * bottom * M_PI * 4.0f / 3.0f;
    }
};


int main() 
{
	double width;
	double heigth;
	double depth;
	double bottom;

	cout << "直方体の幅" << endl;;
	cin >> width;
	cout << "直方体の高さ" << endl;;
    cin >> heigth;
	cout << "直方体の奥行" << endl;;
	cin >> depth;
	Box* box = new Box(width,heigth,depth);
	cout << "直方体の表面積は" << box->GetSurface() << endl;
	cout << "直方体の体積は" << box->GetVolume() << endl;

	cout << "円柱の半径" << endl;;
	cin >> bottom;
	cout << "円柱の高さ" << endl;;
	cin >> heigth;
	Cylinder* cylinder = new Cylinder(bottom, heigth);
	cout << "円柱の表面積は" << cylinder->GetSurface() << endl;
	cout << "円柱の体積は" << cylinder->GetVolume() << endl;

	cout << "円錐の半径" << endl;;
	cin >> bottom;
	cout << "円錐の高さ" << endl;;
	cin >> heigth;
	Cone* cone = new Cone(bottom, heigth);
	cout << "円錐の表面積は" << cone->GetSurface() << endl;
	cout << "円錐の体積は" << cone->GetVolume() << endl;

	cout << "球の半径" << endl;;
	cin >> bottom;
	Sphere* sphere = new Sphere(bottom);
	cout << "球の表面積は" << sphere->GetSurface() << endl;
	cout << "球の体積は" << sphere->GetVolume() << endl;
	return 0;
}
