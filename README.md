# ARDUINO-NO8
這次的題目分三個步驟</p>
step1自動轉換顏色(至少6種顏色</p>
step2呼吸燈</p>
step3按一下按鈕換一種顏色(至少六種顏色</p>
步驟的更替也以按按鈕的形式呈現</p>
程式如下</p>
</p>

void setup() {</br>
  for(int i=2;i<4;i++)</br>
  pinMode(i,OUTPUT);</br>
  pinMode(8,INPUT);</br>
  pinMode(9,INPUT);</br>
  digitalWrite(8,1);</br>
  digitalWrite(9,1);</br>
}</br>
int x =0;</br>
int s =-15;</br>
int m = 255;</br>
int ch = 1;</br>
</br>
void loop() {</br>
  if(digitalRead(8)==0)</br>
  {</br>
    while(digitalRead(8)==0)delay(50);</br>
    x++;</br>
    if(x>3)x=1;</br>
   </br>
  }</br>
   mod(); </br>
}</br>
void led(int a,int b,int c)</br>
{</br>
  analogWrite(2,a);</br>
  analogWrite(3,b);</br>
  analogWrite(4,c);</br>
}</br>
void mod()</br>
{</br>
  switch(x)</br>
  {</br>
    case 1:</br>
      led(150,0,0);  delay(300);</br>
      led(0,150,0);  delay(300);</br>
      led(0,0,150);  delay(300);</br>
      led(150,150,0);delay(300);</br>
      led(0,150,150);delay(300);</br>
      led(150,0,150);delay(300);</br>
      break;</br>
    case 2:</br>
      if(m>=255||m<=0){s=-s;}</br>
      m=m-s;</br>
      analogWrite(3,m);</br>
      delay(70);</br>
      led(0,0,0);</br>
      break;</br>
    case 3:</br>
      if(digitalRead(9)==0)</br>
      {</br>
        while(digitalRead(9)==0)delay(50);</br>
          ch++;</br>
          if(ch>6)ch=1;</br>
      }</br>
      switch(ch)</br>
      {</br>
        case 1:{ led(150,0,0); break;}</br>
        case 2:{led(0,150,0); break;}</br>
        case 3:{led(0,0,150); break;}</br>
        case 4:{led(150,150,0);break;}</br>
        case 5:{led(150,0,150);break;}</br>
        case 6:{led(150,150,150); break;}</br>
      }</br>
  }</br>
}</br>
