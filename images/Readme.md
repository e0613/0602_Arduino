
# LED 예제 1

## LED 깜빡이기



```C

#define LED_BUILTIN 8
#define SIZE 2


int pin_SW[2] = {2,3};
int pin_LED[2] = {8,9};
int val; // 버튼 감지 변수
int select; // select case문 변수


void setup()
{
  for(int k = 0 ; k < SIZE ; k++)
  {
  	pinMode(pin_SW[k], INPUT);
  	pinMode(pin_LED[k], OUTPUT);
  }
}

void loop()
{
	// 누른 버튼 감지
  	for(int i = 0 ; i < SIZE ; i++)
    {
      val = digitalRead(pin_SW[i]); // return 1 / 0
      bitWrite(select, i, val); // select변수의 i번째 비트에 val를 할당
    }
  
  	switch(select)
    {
      case 1 : 
      	digitalWrite(pin_LED[0], HIGH);
      break;
      case 2 : 
      	digitalWrite(pin_LED[1],HIGH);
      break;
      default:
      	for(int i = 0; i < SIZE ; i++)
        {
          digitalWrite(pin_LED[i],LOW);
        }
      	break;
    }
  
 
  
  
}

```

` : 백틱 
~ : 틸드

" : double quotation
' : single quotation
