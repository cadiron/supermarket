# supermarket

/*实现描述超市的的类Supermarket类，记录系统中现有商品(用指针实现)，定义增加商品的函数Append，
删除商品的函数Delete，查询商品的函数Query，  显示查询结果；   2. 定义商品类Goods，具有商品名称Name，
商品价格 Price  ，商品数量 number 等属性，操作Sale（销售商品，余额不足时给予提示）、
Add（商品上架操作） 和ShowMe（显示商品信息）。  3. 编写main函数，测试以上所要求的各种功能
，完成商品的增加、删除和查询商品，以及商品销售和商品上架的操作。  4. 可以利用对象成员来实现。
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
public:
	Goods(char * name="no name",int price=0,int number=0)
	{
		strcpy(Name,name);
		Price=price;
		Number=number;
	}
	void Sale();
	Good* Add();
	void ShowMe();
};


class Supermarkets
{
private:
	Goods * pFirst;
public:
	void Append();
	void Delete();
	void Query();
};

Goods::Goods(){}

Goods::~Goods(){}

void Goods::Add()//商品上架操作
{
	cout<<"########请输入待上架商品的信息#######"<<endl;
	cout<<"####请输入商品的名称：";
	cin>>Name;
	cout<<"####请输入商品数量：";
	cin>>Number
	cout<<"####请输入商品价格：";
	cin>>Price;
}

int Goods::Sale()//销售商品，余额不足时给予提示
{

	int num;//purchase quantity
	cout<<"输入要购买商品的数量：";
	cin>>num;
	if(num>Number)
	{
		cout<<"sorry，我们不够货啦！";
		return 
	}
		else
		Number-=num;

}
void Goods::ShowMe()//显示商品信息
{
	cout<<"####商品的名称	商品数量	商品价格";
	cout<<Name<<"	"<<Number<<"	  "<<Price<<endl;
}


int main()
{
	Goods gs("天地一号",5,24);
	gs.ShowMe();
	gs.Sale();
	gs.ShowMe();
	return 0;
}
