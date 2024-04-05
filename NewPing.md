# NewPing-
```언어
#include <NewPing.h>  //Neping 라이브러리를 추가

#define TRIGGER_PIN  12  //트리거 핀을 12번 핀으로 설정

#define ECHO_PIN     11  //에코 핀을 11번 핀으로 설정

#define MAX_DISTANCE 100  //최대 측정 거리를 100cm로 설정

NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

void setup() {
  Serial.begin(115200);  //시리얼 통신을 115200 보드레이트로 설정
}

void loop() {
  float distance = 0.0;

  delay(50);

  distance = sonar.ping_cm();
  if(distance ==0) distance = MAX_DISTANCE;  //뉴핑은 물체와의 거리가 인식이 안될 때, 0을 출력한다. 따라서 0이 출력될 때, 최대 측정 거리가 출력되도록 설정

  Serial.print("Ping: ");
  Serial.print(distance);
  Serial.println("cm");
}
```
