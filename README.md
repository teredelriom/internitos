# 🏥 Internitos Pro

**Internitos Pro** es una suite de herramientas de escritorio diseñada para **internos de medicina y personal de salud**. Su objetivo es optimizar el flujo de trabajo clínico diario, centralizando calculadoras, guías, gestión de fichas y utilidades administrativas en una interfaz moderna y rápida.

Construido con **Python** y **Flet**, funciona de manera local y segura, ideal para entornos hospitalarios con conectividad limitada.

---

## ✨ Características Principales

La aplicación cuenta con 8 módulos especializados:

* **🏠 Dashboard (Inicio):** Resumen del turno, accesos rápidos y KPIs de pacientes (Ingresos, Pendientes, Altas).
* **📝 Ficha Clínica:** Generador de evoluciones y notas de ingreso con plantillas autocompletables (insuficiencia cardíaca, neumonía, etc.).
* **🧪 Laboratorio:** Interpretación automática de exámenes. Detecta AKI, trastornos ácido-base, anemias y patrones hepáticos.
* **📚 Guías Clínicas:** Visor de protocolos en Markdown con soporte para flujogramas (Graphviz).
* **🧮 Calculadoras:** Herramientas esenciales validadas:
    * *Renal:* Cockcroft-Gault, FeNa.
    * *Cardio:* PAM, QTc Bazett.
    * *UCI:* Bombas de infusión y drogas vasoactivas.
* **📞 Directorio Seguro:** Agenda telefónica hospitalaria con cifrado de contraseñas y anexos.
* **⚡ Electrocardiograma:** Calculadora de Eje, Frecuencia y QTc, con tablas de referencia (paredes de infarto, bloqueos).
* **💉 Procedimientos:** Checklists de seguridad y generador de notas para procedimientos comunes (Paracentesis, CVC, PL).

---

## 🛠️ Instalación y Requisitos

### Prerrequisitos
* **Python 3.8+** instalado en el sistema.
* (Opcional) **Graphviz** instalado y agregado al PATH (para visualizar flujogramas en el módulo de Guías).

### Pasos de Instalación

1.  **Clonar o descargar el repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/internitos-pro.git](https://github.com/tu-usuario/internitos-pro.git)
    cd internitos-pro
    ```

2.  **Crear un entorno virtual (Recomendado):**
    ```bash
    # En Windows
    python -m venv venv
    venv\Scripts\activate

    # En Mac/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Instalar dependencias:**
    ```bash
    pip install -r Internitos/requirements.txt
    ```

    > **Nota:** Si tienes problemas instalando `cryptography` o `graphviz`, la aplicación funcionará en "Modo Compatibilidad" (sin cifrado fuerte o sin diagramas), pero se recomienda instalarlos para la experiencia completa.

---

## 🚀 Ejecución

Para iniciar la aplicación, ejecuta el siguiente comando desde la carpeta raíz del proyecto:

```bash
python Internitos/main.py

```

---

## 📂 Estructura del Proyecto

```text
Internitos/
├── assets/             # Recursos estáticos (fuentes, iconos, DB inicial)
├── data/               # Bases de datos JSON por defecto
├── utils/              # Lógica auxiliar
│   ├── calculations.py # Motor matemático clínico
│   ├── persistence.py  # Gestor de base de datos y fusión de datos
│   └── theme.py        # Sistema de diseño (colores, estilos)
├── views/              # Vistas de la interfaz (Flet)
│   ├── home_view.py
│   ├── ficha_view.py
│   ├── laboratorio_view.py
│   └── ... (otros módulos)
├── main.py             # Punto de entrada de la aplicación
└── requirements.txt    # Librerías necesarias

```

---

## 💾 Persistencia de Datos

Internitos Pro guarda la información del usuario (contactos, plantillas personalizadas, guías) en el directorio seguro del sistema operativo:

* **Windows:** `%APPDATA%\InternitosPro\`
* **Mac/Linux:** `~/.InternitosPro/`

El sistema cuenta con una lógica de **"Smart Merge"**: Si actualizas la aplicación, tus datos personales NO se borran. El sistema fusiona las novedades de la actualización con tus registros existentes.

---

## 🛡️ Seguridad

* **Directorio:** Utiliza la librería `cryptography` (Fernet) para cifrar las contraseñas guardadas en el directorio telefónico localmente.
* **Local-First:** Ningún dato del paciente sale de tu computadora. Todo el procesamiento es local.

---

## 🤝 Contribución

¡Las contribuciones son bienvenidas! Si tienes una nueva calculadora médica o una mejora en la interfaz:

1. Haz un Fork del proyecto.
2. Crea una rama (`git checkout -b feature/nueva-calc`).
3. Haz tus cambios y commit (`git commit -m 'Agrega calculadora de Dosis Pediátrica'`).
4. Haz Push (`git push origin feature/nueva-calc`).
5. Abre un Pull Request.

---

**Desarrollado con ❤️ para la Medicina.**

```

```
