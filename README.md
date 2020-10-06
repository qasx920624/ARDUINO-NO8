# ARDUINO-NO8
這次的題目分三個步驟</p>
step1自動轉換顏色(至少6種顏色</p>
step2呼吸燈</p>
step3按一下按鈕換一種顏色(至少六種顏色</p>
步驟的更替也以按按鈕的形式呈現</p>
程式如下</p>
</p>

```c++
void setup() {
for(int i=2;i<4;i++)
pinMode(i,OUTPUT);
pinMode(8,INPUT);
pinMode(9,INPUT);
digitalWrite(8,1);
digitalWrite(9,1);
}
int x =0;
int s =-15;
int m = 255;
int ch = 1;

void loop() {
if(digitalRead(8)==0)
{
while(digitalRead(8)==0)delay(50);//★防彈跳★
x++;
if(x>3)x=1;

}
mod();
}
void led(int a,int b,int c)
{
analogWrite(2,a);
analogWrite(3,b);
analogWrite(4,c);
}
void mod()
{
switch(x)
{
case 1://step1程式部分
led(150,0,0); delay(300);
led(0,150,0); delay(300);
led(0,0,150); delay(300);
led(150,150,0);delay(300);
led(0,150,150);delay(300);
led(150,0,150);delay(300);
break;
case 2://step2程式部分
if(m>=255||m<=0){s=-s;}
m=m-s;
analogWrite(3,m);
delay(70);
led(0,0,0);
break;
case 3://step3程式部分
if(digitalRead(9)==0)
{
while(digitalRead(9)==0)delay(50);
ch++;
if(ch>6)ch=1;
}
switch(ch)
{
case 1:{ led(150,0,0); break;}
case 2:{led(0,150,0); break;}
case 3:{led(0,0,150); break;}
case 4:{led(150,150,0);break;}
case 5:{led(150,0,150);break;}
case 6:{led(150,150,150); break;}
}
}
}
```

