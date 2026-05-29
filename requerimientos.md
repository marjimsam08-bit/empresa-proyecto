Documento de Especificación de Producto: App "QR-Safe Contact"
1. Resumen Ejecutivo
Aplicación web tipo PWA diseñada para operar 100% offline, enfocada en la gestión de etiquetas físicas vinculadas a vehículos. Permite cifrar información de contacto en un código QR, imprimirlo en formato térmico y recuperar los datos mediante escaneo.

2. Requerimientos Técnicos Principales
Arquitectura: PWA (Progressive Web App) con soporte Service Worker para funcionamiento offline estricto.

Hosting: Compatible con despliegue en GitHub Pages (estático).

Almacenamiento Local: Uso de IndexedDB para la persistencia segura de la clave de cifrado (gestión de llaves maestra).

3. Módulos Funcionales
A. Sección: Configuración (Settings)

Gestión de Llave: Entrada tipo password para definir la clave de cifrado/descifrado.

Persistencia: La llave debe almacenarse en IndexedDB para asegurar que el usuario no deba reingresarla tras cerrar el navegador.

B. Sección: Generar QR

Input de Datos: Formulario para Nombre, Teléfono y Placa (ID de etiqueta).

Procesamiento: * Generar objeto JSON con los datos del contacto.

Cifrado del objeto JSON usando la llave almacenada.

Generación de QR a partir de la cadena cifrada.

Impresión: Salida optimizada para impresora térmica (etiqueta física).

Nota: La placa vehicular se incluirá como texto plano (legible) junto al QR impreso.

C. Sección: Leer y Desencriptar

Escaneo: Interfaz de cámara para lectura de QR.

Desencriptación: Procesamiento del contenido del QR usando la llave persistida.

Visualización:

Despliegue del contacto.

Acción rápida: El número de teléfono será un enlace con protocolo tel: para llamada directa al hacer clic.
