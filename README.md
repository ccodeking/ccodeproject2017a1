## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/ccodeking/ccodeproject2017a1/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ccodeking/ccodeproject2017a1/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

# C Code Project Class 2017.11.7  

lecturer : Peter (cell : 0979050902 ; e-mail : rd02nvc2@gmail.com)

第一章:輸出入及宣告

第一節:宣告

一個最基本的的C程式長相如下

void main(void)

{

}
void main(void)

^^^^      ^^^^

第一個void代表main這個函式不會傳回數值

第二個void代表main這個函式不需要任何參數

兩個大括號中間用來放程式碼{ }

C語言中,提供了下列幾種最基本的儲存數值的型態

這個程式可以清楚看到各種型態在記憶體中的實際2進位儲存情形 [bitview]

type	在32位元的PC作業系統下, 通常能記錄的數值範圍

char	佔1位元, 可記錄-128....127之間的數值

unsigned char	佔1位元, 可記錄0...255之間的數值

short	佔2位元, 可記錄-32768....32767之間的數值

unsigned short	佔2位元, 可記錄0....65536之間的數值

int	佔4位元, 可記錄-2147483648....2147483647之間的數值

unsigned int	佔4位元, 可記錄0....4294967295之間的數值

long	佔4位元, 可記錄-2147483648....2147483647之間的數值

unsigned long	佔4位元, 可記錄0....4294967295之間的數值

float	佔4位元, 可記錄 1.175494351e-38....3.402823466e+38 or -1.175494351e-38....-3.402823466e+38

double	佔8位元, 可記錄2.2250738585072014e-308....1.7976931348623158e+308 or -2.2250738585072014e-308....-1.7976931348623158e+308

向電腦要求一塊記錄數值的記憶體空間叫做宣告, 舉例如下


void main(void)

{
	// 向電腦要一塊能放整數的記憶體, 這個位置中放的東西用i來代表
	
	int i;
	
	// 向電腦要一塊能放字元的記憶體, 這個位置中放的東西用c來代表
	
	char c;
	
	// 向電腦要一塊能放浮點數的記憶體, 這個位置中放的東西用f來代表
	
	float f;
	
	// 向電腦要一塊能放長浮點數的記憶體, 這個位置中放的東西用d來代表
	
	double d;
	
	
	// 設定i中放的數值為100
	
	i=100;
	
	// 設定c中放的字元為字母a, 兩個單引號' '中間的東西叫字元
	
	c='a';
	
	// 設定f中放的數值為1.5
	
	f=1.5;
	
	// 設定d中放的數值為1.5
	
	d=1.5;
	
}

設定數值可以在宣告時同時做, 舉例如下


void main(void)

{
	int i=100;
	
	char c='a';
	
	float f=1.5;
	
	double d=1.5;
	
}

設定數值時可以帶入一個數學算式

void main(void)

{

	int i=10+2*3; // 設定i=16
	
	char c='a'+1 // 設定c=98+1=99=字元'b'的ASCII值
	
}

第二節:輸出Output

想辨法從電腦發出訊息叫做輸出, 像是在螢幕上印出一些字, 在螢幕上畫圖, 從音效卡發出聲音.....都算是輸出.

C語言的標準函式庫中提供了最簡單的輸出函式是printf, 可以在螢幕上印出一些字.


// stdio.h中有定義printf函式中所需要的參數型態

#include < stdio.h >

void main(void)
{
	printf("hello\n");
	
	//      ^^^^^^^  這些字都會被印出來, \n是換行符號
	
	// 兩個雙引號" "中間的東西叫做字串
	
}

printf中除了可以放一個寫好的字串之外, 還可以拿來印出宣告好的變數內容.

#include < stdio.h >

void main(void)

{
	int i=100;
	
	printf("i = %d \n", i);
	
	//	^^^  ^^
	
	//	|   %d是一個符號,代表要在字串結束後去找一個整數的變數來印
	
	//	i = 這一部分會直接印出來
	
}

printf字串中常使用的符號有

符號	可以拿來印的東西

%d	印出整數

%u	印出無負號的整數

%c	印出字元

%x	印出16進元的整數

%f	印出浮點數

%lf	印出長的浮點數

%e	用科學記號來輸出浮點數

舉例如下

#include < stdio.h >

void main(void)
{
	int i=100;
	
	char c='A';
	
	float f=1.5;
	
	double d=3.0;
	
	printf("%d %c %f %lf", i, c, f, d);
}

輸入Input

想辨法傳送訊息給電腦叫做輸入input, 像是敲鍵盤, 動滑鼠...都算是輸入. C語言的標準函式庫提供最簡單的輸入函式是scanf.

#include < stdio.h >

void main(void)

{
	int i;
	
	scanf("%d", &i);
	
}

上面的例子就可以從鍵盤讀一個整數給電腦. &i的意思是要叫電腦把讀到的數字放進變數i的記憶體位置中. &在此是"取出變

數的記憶體位址"的意思.

scanf中同樣要放一個字串, 通常都只會放符號(就如同printf中的符號一樣). 

舉例如下:

#include < stdio.h >

void main(void)

{

	int i;
	
	char c;
	
	float f;
	
	double d;
	
	
	scanf("%d %c %f %lf", &i, &c, &f, &d);
	
	// 分別讀入1個整數, 1個字元, 1個浮點數, 1個長浮點數
	
}

scanf的字串中放入其它字元有時候沒有意義

#include < stdio.h >

void main(void)
{
	int a,b;
	
	scanf("%d,%d", &a, &b);
	
	//      ^^^ 逗號在此有意義,代表兩個數字之間用逗號來區隔 ex: input 36,35 get a=36 b=35
	
	scanf("%d %d\n", &a, &b);
	
	//          ^^換行符號在此沒有意義, 會導致scanf無法停止
	
}



範例:輸入正方形的一個邊長, 算出這個正方形的面積.

#include < stdio.h >

void main(void)

{

	int i;
	
	scanf("%d",&i);
	
	printf("area=%d\n", i*i);
	
}



第三節:C語言中的數學

基本數學

和四則運算的原則一樣, 先做*/後做+-

ex: a=3+4*2, a=11;

C語言中要改變運算的優先順序, 只有小括號可以使用()

ex: a=(3+4)*2, a=14; a=(3+4*(2+1))*2, a=30

要取除法的餘數用"%"來做

ex: a=5%3 ,a=2, 因為5除以3會餘2

特殊寫法


a++; // 先把a的值送出去後, 再把a自己加上1

a--; // 先把a的值送出去後, 再把a自己減去1

++a; // 先把a自己加上1後, 再把a的值送出去

--a; // 先把a自己減去1後, 再把a的值送出去


範例:

void main(void)

{
	int a=5;
	
	int b=a++; // b=5, a=6
	
	int c=a--; // c=6, a=5
	
	int d=++a; // d=6, a=6
	
	int e=--a; // e=5, a=5
	
}


還有一些在設定數值時的特殊寫法

a+=1 // 相當於a=a+1;

a*=2 // 相當於a=a*2;

其它以此類推



位元運算

位元運算要從二進位的儲存方式去看, 舉例如下:

&(AND)運算

2進元值	10進位值

0010	2

&	0011	3

---------------------

0010	2

|(OR)運算

2進元值	10進位值

0010	2


|	0011	3

---------------------

0011	3

~(FLIP)反相

2進元值	10進位值

0010	2

---------------------

1101	13



範例:

void main(void)
{
	int a=4; // a=0100b
	
	int b=8; // b=1000b
	
	int c=a | b; // c= 0100b | 1000b = 1100b = 12
	
	int d=a & b; // d= 0100b & 1000b = 0000b = 0
	
}

還有移動位元的運算

a=1<<2 // 把1往左移動2個位元  a = 0001b<<2 = 0100b = 4

a=8>>1 // 把8往右移動1個位元  a = 1000b>>1 = 0100b = 4

a<<=1  // 相當放a=a<<1, 結果會等於a=a*2

a>>=3  // 相當於a=a>>3, 結果會等於a=a/8



