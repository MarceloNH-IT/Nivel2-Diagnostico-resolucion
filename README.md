# 🌐 Configuración Básica de IP en Linux – Nivel 2

Esta práctica demuestra cómo un operador de nivel 2 puede:
- Detectar fallos de conectividad más allá de la configuración básica.
- Revisar tabla de rutas y configuración del hipervisor.
- Aplicar correcciones en VirtualBox (NAT/Bridge).
- Validar nuevamente con ping y nslookup.
- Documentar tanto errores como soluciones.

# 🖧 Laboratorio NOC – Nivel 2  
Diagnóstico y resolución de red desconectada en máquina virtual

## 📌 Descripción
Este laboratorio reproduce un escenario típico de **NOC Nivel 2**:  
- La máquina virtual Linux no tenía conectividad porque la interfaz de red estaba **desconectada** en la configuración de virtualización.  
- Se realizó diagnóstico paso a paso, identificación del fallo y resolución aplicando cambios en la VM y validando conectividad.

## 🎯 Objetivos
- [Detectar fallo de conectividad](ca://s?q=Detectar_fallo_de_conectividad_en_Linux)  
- [Revisar configuración de red en VM](ca://s?q=Revisar_configuracion_de_red_en_virtualizacion)  
- [Aplicar corrección en interfaz desconectada](ca://s?q=Corregir_interfaz_de_red_en_virtualizacion)  
- [Validar conectividad con ping y DNS](ca://s?q=Validar_conectividad_con_ping_y_DNS)  

## 🧩 Comandos utilizados
- `ip addr show` → [Ver estado de interfaces](ca://s?q=Comando_ip_addr_show_en_Linux)  
- `ping -c 4 192.168.60.1` → [Probar conectividad con gateway](ca://s?q=Comando_ping_en_Linux)  
- `ping -c 4 google.com` → [Probar conectividad externa](ca://s?q=Ping_a_google_en_Linux)  
- `nslookup google.com` → [Validar resolución DNS](ca://s?q=Comando_nslookup_en_Linux)  

## 🔎 Diagnóstico
- La interfaz aparecía sin IP asignada en `ip addr show`.  
- El ping al gateway fallaba con *Destination Host Unreachable*.  
- Se verificó la configuración de la VM y se detectó que la tarjeta de red estaba **desconectada**.  

## 🔧 Resolución
- Se activó la interfaz de red en la configuración de virtualización.  
- Se aplicó nuevamente la configuración IP estática con Netplan.  
- Se validó conectividad con ping y resolución DNS.  

## ✅ Validación
- Ping exitoso al gateway (`192.168.60.1`).  
- Ping exitoso a dominio externo (`google.com`).  
- DNS respondió correctamente con `nslookup`.  

## 📷 Evidencias
- Captura de `ip addr show` antes y después de la corrección.  
- Resultados de ping fallido y luego exitoso.  
- Validación de DNS con `nslookup`.  

## 📚 Notas
Este laboratorio demuestra la capacidad de **diagnóstico y resolución de incidentes** en entorno virtualizado, documentando el proceso completo como evidencia técnica en portafolio GitHub.


  Ingresamos a Virtualbox configuramos la red.

![Ping Gateway](assets/linux-ip-nivel2/X5.jpeg)
---

## 📊 Paso 1 – Identificación del fallo
**Ping al gateway**
![Ping Gateway](assets/linux-ip-nivel2/X1.jpeg)

**Ping a Google**
![Ping Google](assets/linux-ip-nivel2/X2.jpeg)

**Prueba DNS**
![NSLookup](assets/linux-ip-nivel2/X3.jpeg)

> 📌 Observación: IP y DNS configurados, pero sin salida a Internet.  
> El ping devuelve *Destination Host Unreachable*.

---

## 🛠️ Paso 2 – Diagnóstico avanzado

    ip route show
 
👉 Captura: salida mostrando la tabla de rutas.

📌 La ruta por defecto existe, pero el gateway no responde.

🔧 Paso 3 – Reparación en VirtualBox
Cambio de adaptador a NAT
[Parece que el resultado no era seguro para mostrar. ¡Cambiemos de enfoque y probemos algo diferente!]

## 📌 Se modificó la configuración de red en VirtualBox para permitir salida a Internet.

## 📌 Paso 4 – Validación después de la reparación

# Prueba de conectividad externa (Google DNS)
    ping -c 4 8.8.8.8
[Parece que el resultado no era seguro para mostrar. ¡Cambiemos de enfoque y probemos algo diferente!]
# Prueba de conectividad a un dominio (Google)
    ping -c 4 google.com
[Parece que el resultado no era seguro para mostrar. ¡Cambiemos de enfoque y probemos algo diferente!]
# Prueba de resolución de nombres
    nslookup google.com
[Parece que el resultado no era seguro para mostrar. ¡Cambiemos de enfoque y probemos algo diferente!]
# Revisión de tabla de rutas
    ip route show
[Parece que el resultado no era seguro para mostrar. ¡Cambiemos de enfoque y probemos algo diferente!]
📌 Observación: Tras cambiar el adaptador a NAT en VirtualBox, la VM recuperó salida a Internet y resolución de nombres.

    Ping a 8.8.8.8 → exitoso.

    Ping a google.com → exitoso.

    Nslookup → resolvió correctamente.

## ✅ Conclusión Nivel 2
El práctico de nivel 2 demuestra que un operador puede:

Detectar fallos de conectividad más allá de la configuración básica.

Revisar tabla de rutas y confirmar que el problema estaba en el hipervisor.

Aplicar correcciones en VirtualBox (NAT/Bridge).

Validar nuevamente con ping y nslookup.

Documentar tanto errores como soluciones, dejando evidencia clara.

## 📌 Observación: En entornos virtuales, la conectividad depende tanto del sistema operativo como de la configuración del hipervisor. El operador nivel 2 debe diagnosticar ambos niveles.

## 📚 Notas
Este laboratorio demuestra la capacidad de **diagnóstico y resolución de incidentes** en entorno virtualizado, documentando el proceso completo como evidencia técnica en portafolio GitHub.


## 📊 Paso 5 – Contadores y stats

## 📈 Contadores de pruebas
- Total de comandos ejecutados: 18  
- Total de capturas subidas: 12  
- Validaciones exitosas: 9  
- Errores documentados: 3
  

![Configuración del Adaptador de Red Puente](FotoNOC.jpg)
## 🤝 Conclusión y Contacto

![GitHub Stats](https://github-readme-stats.anuraghazra1.vercel.app/api?username=MarceloNH-IT&show_icons=true&theme=radical)

![Top Languages](https://github-readme-stats.anuraghazra1.vercel.app/api/top-langs/?username=MarceloNH-IT&layout=compact&theme=radical)

![Streak Stats](https://github-readme-streak-stats.herokuapp.com/?user=MarceloNH-IT&theme=radical)

![Profile Views](https://komarev.com/ghpvc/?username=MarceloNH-IT&color=blue&style=flat)


![Ping Gateway](FotoNOC.jpg)

* **💼 LinkedIn**: [Horacio Marcelo Nuñez](https://linkedin.com) 
* **📬 Correo Electrónico**: [marcelonh86@gmail.com](marcelonh86@gmail.com)
* **🚀 GitHub**: [@MarceloNunez-NOC](https://github.com/MarceloNunez-NOC)

Agradezco el tiempo de quienes visitan mi portafolio en GitHub. Cada laboratorio refleja mi compromiso con el aprendizaje continuo y la práctica aplicada en IT, redes y administración de sistemas. Mi objetivo es demostrar que puedo diagnosticar, resolver y documentar incidentes de manera profesional, utilizando máquinas virtuales y configuraciones de red.

Invito a reclutadores y colegas a seguir mis repositorios, donde iré compartiendo nuevos proyectos, certificados y logros. Estoy abierto a colaborar y aportar mi experiencia en entornos que valoren la constancia y la capacidad de resolver problemas.
