# MLSec-NIDS-Lab: Machine Learning for Security en Ciberdefensa
## Del Ciclo de Datos a un NIDS Automatizado en Cyber Range

> **Laboratorio práctico de MLSec:** Construcción de un Sistema de Detección de Intrusos (NIDS) desde cero, interceptando telemetría de red con Scapy y clasificando ciberataques utilizando Random Forest y Scikit-Learn.

### 📌 Descripción General
Este laboratorio práctico recorre de forma rigurosa el ciclo completo de la ciencia de datos aplicada a la **Defensa, Inteligencia y Gobierno** (Ciberdefensa). Diseñado para guiar tanto a perfiles en formación como a profesionales avanzados, el recorrido abarca desde la captura de telemetría de red en tiempo real, pasando por el Análisis Exploratorio de Datos (EDA) y la Ingeniería de Características, hasta el entrenamiento y despliegue de modelos predictivos.

A diferencia de un IDS genérico o centrado en el host, este sistema opera a nivel de red (**NIDS**). Analiza el tráfico bruto (*raw packets*) y los flujos de comunicación para detectar patrones anómalos e intentos de intrusión de manera automatizada mediante inteligencia artificial.

### 🎯 Objetivos del Proyecto
*   **Captura de Telemetría:** Interceptar tráfico de red (*sniffing*) en tiempo real extrayendo características fundamentales como IPs, puertos y protocolos.
*   **Análisis y Procesamiento:** Estructurar la información extraída mediante ingeniería de características para su evaluación analítica y visual.
*   **Clasificación Predictiva:** Entrenar un algoritmo de aprendizaje supervisado para detectar secuencias maliciosas (como escaneos de red), evaluando su rendimiento mediante métricas especializadas.

### 📊 Nivel de Dificultad
Este laboratorio está diseñado para que puedas ejecutarlo y comprenderlo de punta a punta. Aunque no requiere experiencia previa avanzada, se recomienda tener nociones básicas de informática y redes para instalar los entornos y comprender la lógica de cada proceso. Además, se recomienda explorar la bibliografía y los recursos sugeridos para profundizar y enriquecer el conocimiento general de lógica detrás de cada proceso.
*   Ciberseguridad | Redes: **Básico**
*   Ciencia de Datos: **Básico / Medio**

### 🛠️ Stack Tecnológico
*   **Entorno y Redes:** Kali Linux (Atacante), Metasploitable (Objetivo), VirtualBox.
*   **Manipulación de Datos de Red:** Scapy (Python).
*   **Procesamiento y Visualización:** Pandas, NumPy, Seaborn, Matplotlib.
*   **Machine Learning:** Scikit-Learn (Random Forest, Pipelines, StandardScaler).
*   **Concurrencia:** Hilos (`threading`) para monitoreo y ataque simultáneo.

### ⚠️ Requerimientos, Seguridad y Ética

**1. Entorno Aislado (Cyber Range)**  
Es **obligatorio** contar con un hipervisor como [VirtualBox](https://www.virtualbox.org/) con 2 máquinas virtuales configuradas en "Red Interna" (aislada, se debe comprobar la respuesta al *ping*):
*   **VM Atacante (`10.0.0.4`):** [Kali Linux](https://www.kali.org/).
*   **VM Objetivo (`10.0.0.5`):** [Metasploitable](https://sourceforge.net/projects/metasploitable/).

**2. Configuración del Entorno Python**  
Se requiere [Jupyter Notebook](https://jupyter.org/) ejecutado con privilegios de administrador (`root`) para permitir la inspección profunda de paquetes.
*   Instalar Jupyter: `pip3 install jupyter`
*   Crear y activar entorno virtual: `python3 -m venv env` ➔ `source env/bin/activate`
*   Instalar dependencias: `pip3 install pandas numpy scapy seaborn matplotlib scikit-learn joblib` *(Módulos como `random`, `threading`, etc., vienen por defecto).*
*   Ejecución (*ejemplo*): `cd ~/ia_cyber_range && sudo ./env/bin/jupyter notebook --allow-root`
*   Acceso: Ingresar desde `http://localhost:8888` en el navegador.
*   *Nota:* En caso de error de *socket* en Jupyter, cierre el entorno y vuelva a ejecutarlo asegurándose de tener los permisos de `root`.

**3. Prohibición de Nube Pública**  
**NO** ejecute este código en entornos 100% *cloud* (como Google Colab, AWS, Azure). La generación de tráfico ofensivo y la apertura de *raw sockets* violan los términos de servicio de la mayoría de los proveedores y resultarán en la suspensión inmediata de su cuenta.

**4. Uso Responsable**  
Este laboratorio ha sido diseñado con fines estrictamente académicos y de investigación en ciberdefensa. La ejecución en un marco de aislamiento garantiza la seguridad de los procesos y el cumplimiento ético-legal. El autor no se hace responsable del mal uso del material. Todo el código, las librerías y la información utilizada son de acceso público y libre.
