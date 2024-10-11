# UNIDAD_3_SFI_MBN

## Ejercicio 1: introducción a los protocolos binarios - caso de estudio
### ¿Cómo se ve un protocolo binario?
Un protocolo binario es una serie de bits (1 y 0) que se envían entre dispositivos para comunicarse, cada conjunto de bits tiene un significado específico, como un comando, dirección, o datos.

### ¿Puedes describir las partes de un mensaje?
#### Cabecera (Header):
Identificación del tipo de mensaje o la dirección ademas está contiene el Len(longitud), Adr(dirección).
#### Datos (Payload):
Los datos que se transmiten; en está contiene la data[]
#### Checksum/CRC (Footer):
Para la verificación de la integridad, está contiene LSB-CRC16 y MSB-CRC16 los cuales son bytes para los errores

### ¿Para qué sirve cada parte del mensaje?
#### Cabecera (Header):
Sirve para identificar el tipo de mensaje y proporcionar información necesaria para que el usuario/receptor sepa cómo manejar el resto del mensaje.
#### Datos (Payload):
Los datos contienen la información que se está transmitiendo. Por ejemplo, si el sensor está midiendo temperatura, esta parte del mensaje incluirá el valor de la temperatura medida.
#### Checksum/CRC (Footer):
Esta parte sirve para verificar si los datos se recibieron correctamente. Si hay un error, el usuario/receptor podrá detectar que los datos fueron corrompidos y podrá solicitar que se reenvíe el mensaje.

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
