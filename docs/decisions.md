# ORBIS — Decisiones técnicas

## 1. Objetivo

ORBIS será un centro de control personal para CachyOS y Hyprland, con integración progresiva con Serpantinum y Quickshell.

El desarrollo priorizará la seguridad, la modularidad, el funcionamiento local y la transparencia de las operaciones.

## 2. Tecnologías

- **Aplicación de escritorio:** Tauri 2.
- **Interfaz:** Svelte 5, TypeScript y Vite.
- **Estilos:** Tailwind CSS.
- **Componentes:** biblioteca accesible compatible con Svelte.
- **Núcleo local:** Rust.
- **Concurrencia:** Tokio, cuando sea necesario.
- **Persistencia:** SQLite y archivos TOML/JSON.
- **Configuración:** `~/.config/orbis/`.
- **Control de versiones:** Git.

## 3. Arquitectura y seguridad

- La interfaz solicitará operaciones mediante comandos Tauri tipados.
- El backend validará las peticiones y los parámetros.
- Las operaciones estarán registradas y limitadas por capacidades explícitas.
- La interfaz y la IA no podrán ejecutar comandos de shell arbitrarios por su cuenta.
- Las acciones sensibles o destructivas requerirán confirmación.
- Los resultados y errores importantes deberán poder consultarse.
- Los secretos no se guardarán en Git ni en archivos de configuración en texto plano.

## 4. Principios de desarrollo

- Implementar funciones pequeñas y verificables.
- Comprobar cada etapa antes de continuar.
- Evitar duplicar tecnologías o mantener dos backends generales.
- No asumir que las herramientas del sistema están instaladas: detectarlas.
- Mantener las operaciones reversibles cuando sea posible.
- Documentar las decisiones que cambien la arquitectura.

## 5. Orden inicial de trabajo

1. Preparar la interfaz y sus componentes.
2. Establecer una estructura modular.
3. Definir el contrato seguro de acciones del backend.
4. Crear una paleta de comandos y búsqueda de aplicaciones.
5. Añadir consultas reales del sistema y búsqueda de paquetes.
6. Incorporar confirmaciones, registros y pruebas.

## 6. Estado actual

- Repositorio Git inicializado en `main`.
- Plantilla Tauri 2 + Svelte + TypeScript creada.
- Dependencias instaladas.
- Frontend comprobado mediante Vite.
- Ventana de Tauri abierta correctamente mediante una variable temporal de compatibilidad gráfica en NVIDIA + Wayland.
- No se han implementado todavía las funciones propias de ORBIS.

## 7. Pendiente

- Configurar Tailwind CSS.
- Seleccionar e instalar la biblioteca de componentes accesible.
- Definir y comprobar el pipeline de pruebas.
- Preparar el primer commit.
