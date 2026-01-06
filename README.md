[⬅️ Volver a "Conceptos de Ladder"](https://github.com/SantiagoBaeza/Conceptos-importantes-de-Ladder/tree/main)

# Uso de temporizadores en PLC – TON, TOF, TP y TONR

Este proyecto muestra cómo utilizar los distintos tipos de **temporizadores** en programación de PLCs para controlar salidas de manera precisa y flexible.  
Los temporizadores permiten retrasar, mantener o generar pulsos de tiempo definidos, siendo fundamentales en la automatización industrial.

---

## Contexto

Se incorporan los temporizadores **TP**, **TON**, **TOF** y **TONR**, aplicados a motores simulados (`motor4`, `motor5`, `motor6`, `motor7`) con una misma condición de entrada (`start button`).  
Cada temporizador se instanció automáticamente desde la barra lateral de instrucciones, generando sus respectivos bloques de datos (`DB1`, `DB2`, `DB3`, `DB4`).  
El tiempo de preset (`PT`) se configuró en **15 segundos** para todos los casos.

---

## Capturas

- **Captura 01**: Segmento 4 y 5 – Temporizadores TP y TON aplicados a `motor4` y `motor5`.  
  ![Segmento 4 y 5 – TP y TON](https://github.com/SantiagoBaeza/Uso-de-temporizadores-en-PLC/blob/main/01%20esquema%20TP%20y%20TON%20instruction%20.jpg)

- **Captura 02**: Segmento 6 y 7 – Temporizadores TOF y TONR aplicados a `motor6` y `motor7`.  
  ![Segmento 6 y 7 – TOF y TONR](https://github.com/SantiagoBaeza/Uso-de-temporizadores-en-PLC/blob/main/02%20esquema%20TOF%20y%20TONR%20instruction%20.jpg)

---

## Funcionalidad

- **TP (Pulse Timer):** genera un pulso de duración fija (15s) al detectar un flanco positivo.  
  - Ideal para activar una salida por tiempo determinado ante un evento puntual.

- **TON (On Delay Timer):** activa la salida después de mantener la condición durante el tiempo de preset.  
  - Si la condición se interrumpe, el temporizador se reinicia.  
  - Es uno de los temporizadores más usados en la industria.

- **TOF (Off Delay Timer):** activa la salida inmediatamente, y la mantiene encendida durante el tiempo de preset **después** de que la condición desaparece.  
  - Requiere un flanco negativo (1→0) para iniciar la cuenta regresiva.

- **TONR (Retentive On Delay):** acumula tiempo mientras la condición esté activa, y **retiene** el valor si se interrumpe.  
  - Solo se reinicia con una señal de reset.  
  - Útil para medir tiempo total de funcionamiento.

---

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)  
- Lógica en escalera (LAD)

---

## Comentarios finales

Este ejercicio demuestra cómo los temporizadores permiten controlar **cuándo** se activan o desactivan las salidas, además de **cómo** se comportan ante cambios de estado.  
La lógica temporal es esencial en procesos industriales, y dominar estos bloques es clave para cualquier perfil técnico en automatización.  

El archivo del proyecto está incluido en este repositorio para que cualquier persona con acceso a **TIA Portal V16** pueda abrirlo y realizar la simulación.  
Este ejercicio tiene como objetivo servir de práctica y dejar registro de mis avances en programación de PLC.

---

> 🧩 Estos espacios están en construcción y se actualizan de forma frecuente.
