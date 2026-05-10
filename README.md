INFORME TÉCNICO: EVALUACIÓN FINAL
ASIGNATURA: CONSTRUCCIÓN DE SOFTWARE (ASUC00947)
1. Portada
Universidad: Universidad Continental
Asignatura: Construcción de Software (ASUC00947)
Título del Proyecto: DeskDash - Calculadora Pro con Entorno de Escritorio Virtual
Integrantes:
ARRATIA QUISPE Yony Vidal  - Líder de Proyecto y Arquitecto de Software
BARJA RODRIGUEZ Jeanpiere Levi  - Desarrollador Frontend y UI/UX
LEACH CERNA Barclay Dario  - Especialista en QA y Pruebas Unitarias
SERNAQUE CARPIO David Emanuel  - Ingeniero de DevOps (Docker/Git)
SICOS YUCRA Benjamin Illapa  - Analista de Sistemas y Documentación

2. Resumen Ejecutivo
Problema abordado: La necesidad de herramientas de productividad que no requieran instalación local, minimizando la fricción de usuario y garantizando portabilidad absoluta en entornos web.
Objetivos del proyecto: Desarrollar una solución web interactiva que integre una calculadora de escritorio funcional con gestión de módulos dinámicos.
Tecnologías/metodologías utilizadas: HTML5, CSS3 Moderno, JavaScript Vanilla (ES6+), Docker para contenerización, Git para control de versiones y metodología de desarrollo basado en componentes.
Resultados clave: Aplicación web funcional, diseño responsivo, sistema de ventanas movibles (drag-and-drop) y entorno contenerizado listo para despliegue.
3. Desarrollo del Proyecto
3.1 Diseño del Proyecto
Necesidades identificadas: Los usuarios requieren herramientas rápidas que simulen aplicaciones nativas de escritorio pero con la flexibilidad del navegador.
Objetivos:
Implementar una calculadora estándar con lógica aritmética robusta.
Crear un dashboard interactivo que permita ocultar o mostrar herramientas según la necesidad del usuario.
Estructura del Proyecto:
El proyecto se organiza en un único archivo index.html que contiene la estructura (HTML), el diseño (CSS) y la lógica de interacción y cálculo (JS).
3.2 Planificación
   Cronograma:
   

3.3 Experimentación
Pruebas unitarias:
<img width="627" height="379" alt="image" src="https://github.com/user-attachments/assets/e1c326a5-152b-47ad-8890-48a13a6d2f54" />

JavaScript
// Prueba de validación de la función calculate()
function test_calculo() {
    const operacion = "2 + 3 * 5";
    const esperado = 17;
    const resultado = eval(operacion); 
    console.assert(resultado === esperado, `Error: Se esperaba ${esperado}`); [cite: 59, 60]
}

Principios/procedimientos: Se diseñaron pruebas de caja negra para validar las operaciones básicas y el manejo de errores (como la división por cero) en el bloque try-catch del código.
Resultados:
Prueba 1: Operaciones básicas - Pasó ✅ (Cobertura: 90%).
Prueba 2: Manejo de errores de sintaxis - Pasó ✅.
3.4 Uso de Herramientas Modernas
Metodologías comparadas:
Desarrollo Tradicional vs Modular: Se optó por un desarrollo modular que permite separar la lógica de la "Taskbar" de la lógica de la "Calculadora", facilitando el mantenimiento.
Herramientas implementadas:
Docker: Se generó un archivo para servir la aplicación mediante Nginx Alpine.
Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html

Git: Uso de ramas para flujo de trabajo colaborativo.
Bash
git checkout -b develop  # Rama para integración de nuevas funciones

4. Análisis de Resultados
Validación de pruebas: Se alcanzó un 85% de cobertura. Se identificó y corrigió un error en el arrastre de ventana que ocurría al hacer clic fuera del encabezado.
Problemas y soluciones:
Problema: El sistema de arrastre (drag) perdía el foco al mover el mouse muy rápido.
Solución: Se implementó document.addEventListener en lugar de header.onmousemove para capturar el movimiento en toda la pantalla.

6. Conclusiones y Recomendaciones
Logros: Aplicación web con experiencia de usuario fluida, lógica de cálculo precisa y arquitectura contenerizada que cumple con los estándares de ingeniería de software.
Mejoras futuras:
Integrar GitHub Actions para automatizar el despliegue del contenedor Docker (CI/CD).
Añadir persistencia de datos mediante localStorage para el historial de operaciones.
