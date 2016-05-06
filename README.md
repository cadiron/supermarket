# supermarket
/*实现描述超市的的类Supermarket类，记录系统中现有商品(用指针实现)，
定义增加商品的函数Append，删除商品的函数Delete，查询商品的函数Query，  
显示查询结果；  
 2. 定义商品类Goods，具有商品名称Name，
商品价格 Price  ，商品数量 number 等属性，操作Sale（销售商品，余额不足时
给予提示）、Add（商品上架操作） 和ShowMe（显示商品信息）。 
 3. 编写main函数，测试以上所要求的各种功能
，完成商品的增加、删除和查询商品，以及商品销售和商品上架的操作。 
 4. 可以利用对象成员来实现。
*/
#include <iostream>
#include <iomanip>
using namespace std;

class Goods
{	
private:
	char Name[20];
	int Price;
	int Number;
	Goods *next;
public:
	Goods(char * name="no name",int price=0,int number=0)
	{
		strcpy(Name,name);
		Price=price;
		Number=number;
		next=NULL;
	}
	void Sale();
	Goods* Add();
	void ShowMe();
};


class Supermarkets
{
private:
	Goods * pFrist;
public:
	Supermarkets(){pFrist=NULL;}
	void Append(Goods gd);
	//void Delete();
	//void Query();
};

void Goods::Sale()
{
	int num;//purchase quantity
	cout<<"please input the purchase quantity";
	cin>>num;
	if(num>Number)
		cout<<"sorry,we don't have enough goods!";
	else
		Number-=num;
}

Goods * Goods::Add()
{	
	cout<<"Goods are addes to the supwemarket"<<endl;
	//要不要对超市进行操作？回答，给个指针试试
	return next;
}

void Goods::ShowMe()
{
	cout<<setw(6)<<Name;
	cout<<setw(6)<<Price;
	cout<<setw(6)<<Number;
}

void Supermarkets::Append(Goods gd)
{
	if(pFrist=NULL)
		pFrist=&gd;
	else
	{
		pFrist.Add()=&gd;
		pFrist=&gd;
	}
}
int main()
{
	Goods gs("天地一号",5,24);
	gs.ShowMe();
	gs.Sale();
	gs.ShowMe();
	return 0;
}
