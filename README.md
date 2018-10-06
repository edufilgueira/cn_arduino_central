# Congfigurar o build arduino via shell

## Instalando o IDE Arduino
```
sudo apt-get update && sudo apt-get upgrade
```

```
sudo apt-get install arduino
```

```
sudo apt-get install avr-libc libftdi1 avrdude openjdk-6-jre librxtx-java
```

## Preparando o arduino pelo terminal

```
sudo apt-get install arduino-mk
```

## Preparando o projeto shell

https://www.youtube.com/watch?v=_EKwvHQctyY

#### 1. criar a pasta sketchbook

```
mkdir sketchbook
```
#### 2. Copiar o arquivo _Arduino.mk_ para a pasta sketchbook criada

```
ln -s /usr/share/arduino/Arduino.mk
```

#### 3. Criar a pasta do projeto
```
mkdir projeto
```

#### 4. Criar o arquivo.ino na pasta do projeto com o programa arduino
Crie o programa que será executado pelo arduino.

#### 5. Criar o arquivo Makefile e escrever nele o seguinte codigo

```
sudo nano Makefile
```

Escreve o seguinte codigo no Makefile
```
BOARD_TAG = mega2560 #uno para arduino uno
ARDUINO_PORT = /dev/ttyACM0 #procurar qual a porta seria disponivel
ARDUINO_LIBS = 
ARDUINO_DIR = /usr/share/arduino/
include ../Arduino.mk
```

#### 6. Rodando a aplicação

Compilar a aplicação

```
make
```

Upload da aplicação

```
sudo make upload
```
