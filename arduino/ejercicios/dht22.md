---
description: Temperatura y Humedad
---

# DHT22

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

```arduino
#include  "DHT.h"             
const  int  DHTPIN  =  2 ;       
const  int  DHTTYPE  =  DHT11 ;  
 
DHT  dht ( DHTPIN ,  DHTTYPE ) ; 
void  setup ( )  { 
  Serial . begin ( 9600 ) ; 
  dht . begin ( ) ;        
}
 
void  loop ( )  {
   float  h  =  dht . readHumidity ( ) ;     
  float  t  =  dht . readTemperature ( ) ; 
 
  Serial . print ( "Temperatura:" ) ; 
  Serial . println ( t ) ;                
  Serial . print ( "Humedad:" ) ; 
  Serial . print ( h ) ;  
  Serial . print ( "%" ) ;       
  Serial . println ( ) ;                
  delay ( 1000 ) ;                      
}
```

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

```arduino
#include  "DHT.h"             
const  int  DHTPIN  =  2 ;       
const  int  DHTTYPE  =  DHT11 ;  

int fanPin = 13;  

DHT  dht ( DHTPIN ,  DHTTYPE ) ;

void  setup ( )  { 
  Serial . begin ( 9600 ) ; 
  dht . begin ( ) ;
  pinMode(fanPin, OUTPUT);  
  digitalWrite(fanPin, LOW);       
}
 
void  loop ( )  {
  float  h  =  dht . readHumidity ( ) ;     
  float  t  =  dht . readTemperature ( ) ; 
 
  Serial . print ( "Temperatura:" ) ; 
  Serial . println ( t ) ;                
  Serial . print ( "Humedad:" ) ; 
  Serial . print ( h ) ;  
  Serial . print ( "%" ) ;       
  Serial . println ( ) ;

  delay(2000);
  
  if (t > 22){  
   digitalWrite(fanPin, HIGH); 
  }  
  else{  
   digitalWrite(fanPin, LOW);
  }        
  delay ( 1000 ) ;                      
}
```
