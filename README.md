# UNIDAD_3_SFI_MBN

## Ejercicio 1: introducción a los protocolos binarios - caso de estudio
### ¿Cómo se ve un protocolo binario?
Un protocolo binario es una serie de bits (1 y 0) que se envían entre dispositivos para comunicarse, cada conjunto de bits tiene un significado específico, como un comando, dirección, o datos.

### ¿Puedes describir las partes de un mensaje?
#### Cabecera (Header):
Identificación del tipo de mensaje o la dirección.
#### Datos (Payload):
Los datos que se transmiten.
#### Checksum/CRC (Footer):
Para la verificación de la integridad, similar al "Footer" que mencionó tu compañero.

### ¿Para qué sirve cada parte del mensaje?

## Ejercicio 4: transmitir números en punto flotante
````
void setup() {
    Serial.begin(115200);
}

void loop() {
// 45 60 55 d5// https://www.h-schmidt.net/FloatConverter/IEEE754.htmlstatic float num = 3589.3645;
static uint8_t arr[4] = {0};

if(Serial.available()){
if(Serial.read() == 's'){
            memcpy(arr,(uint8_t *)&num,4);
            Serial.write(arr,4);
        }
    }
}
````
