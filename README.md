// Detector de Contaminación Sonora
const int micPin = A0;  // Pin donde está conectado el micrófono
const int threshold = 600;  // Umbral para contaminación sonora

void setup() {
  Serial.begin(9600);  // Inicializa la comunicación serial
  Serial.println("Detector de Contaminación Sonora");
}

void loop() {
  int micValue = analogRead(micPin);  // Lee el valor del micrófono
  Serial.print("Valor de sonido: ");
  Serial.println(micValue);  // Muestra el valor en el monitor serial

  // Verifica si el valor supera el umbral
  if (micValue > threshold) {
    Serial.println("¡Contaminación sonora detectada!");
    // Aquí puedes añadir más acciones, como encender un LED o activar un buzzer
  }

  delay(500);  // Espera medio segundo antes de la próxima lectura
}
