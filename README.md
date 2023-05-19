# I2C
integrantes: Valentin Franco/Sebastian Erbino/Thiago Albornoz/Pedro Amenta/Luis Britez
Curso:5°1 Av
#include <stdio.h>
#include "i2c.h"
#include "gpio.h"

// Definiciones de pines GPIO para SDA y SCL
#define I2C0_SDA_PIN 10
#define I2C0_SCL_PIN 11
#define I2C1_SDA_PIN 20
#define I2C1_SCL_PIN 21

// Función para inicializar I2C0 con la velocidad máxima posible
void initI2C0() {
  // Inicializar el periférico I2C0 con la velocidad máxima
  i2c_init(I2C0, I2C_SPEED_FAST);

  // Configurar los pines GPIO para SDA y SCL de I2C0
  gpio_configure_pin(I2C0_SDA_PIN, GPIO_MODE_AF);
  gpio_configure_pin(I2C0_SCL_PIN, GPIO_MODE_AF);

  // Habilitar los pull-up para SDA y SCL de I2C0
  gpio_set_pull(I2C0_SDA_PIN, GPIO_PULL_UP);
  gpio_set_pull(I2C0_SCL_PIN, GPIO_PULL_UP);
}

// Función para inicializar I2C1 con la velocidad máxima posible
void initI2C1() {
  // Inicializar el periférico I2C1 con la velocidad máxima
  i2c_init(I2C1, I2C_SPEED_FAST);

  // Configurar los pines GPIO para SDA y SCL de I2C1
  gpio_configure_pin(I2C1_SDA_PIN, GPIO_MODE_AF);
  gpio_configure_pin(I2C1_SCL_PIN, GPIO_MODE_AF);

  // Habilitar los pull-up para SDA y SCL de I2C1
  gpio_set_pull(I2C1_SDA_PIN, GPIO_PULL_UP);
  gpio_set_pull(I2C1_SCL_PIN, GPIO_PULL_UP);
}

int main() {
  // Inicializar I2C0 y I2C1
  initI2C0();
  initI2C1();

  // Resto del código...

  return 0;
}
