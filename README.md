# 🍽️ Proyecto Final - Estructura de Datos  
**Materia:** LSTI2310  
**Alumno:** [Tu Nombre]  
**Profesor:** [Nombre del profesor]  
**Fecha:** [Mes, Año]  

---

## 📖 Descripción General
Este proyecto consiste en un sistema de **gestión de tareas para un restaurante**, desarrollado en **Java**.  
Se aplican diferentes **estructuras de datos avanzadas (listas, pilas, colas y colas de prioridad)** para organizar, administrar y procesar tareas de manera eficiente.  

El programa cuenta con dos formas de ejecución:  
- **Consola:** interacción básica mostrando la lógica de las estructuras.  
- **Interfaz Gráfica (GUI):** mediante `RestauranteAppGUI.java`, que permite al usuario interactuar con el sistema de manera más visual.  

---

## 🧩 1. Implementación de estructuras  
De acuerdo con la rúbrica, se utilizan **todas las estructuras y algoritmos avanzados necesarios para optimizar operaciones**:  

- **ListaTareas.java**  
  - Implementa una lista dinámica para almacenar y recorrer todas las tareas.  
- **PilaTareas.java**  
  - Gestiona tareas en un esquema **LIFO (Last In, First Out)**.  
  - Ejemplo: si varias órdenes entran al mismo tiempo, la última puede resolverse primero.  
- **ColaTareas.java**  
  - Gestiona tareas en un esquema **FIFO (First In, First Out)**.  
  - Ejemplo: atender clientes en orden de llegada.  
- **ColaPrioridades.java**  
  - Implementa una **cola de prioridad**, donde las tareas urgentes se procesan antes que las normales.  
- **Empleado.java** y **Tarea.java**  
  - Modelan los elementos principales del sistema: trabajadores y actividades del restaurante.  
- **RestaurantePro.java** y **Main.java**  
  - Controlan la lógica principal y la ejecución del programa.  
- **RestauranteAppGUI.java**  
  - Permite la interacción visual con botones y cuadros de texto para agregar, procesar y mostrar tareas.  

📌 Todas estas estructuras trabajan juntas para simular la gestión real de un restaurante.  

---

## 📑 2. Claridad y documentación  
El proyecto está **bien documentado** y presenta claridad en el uso de las estructuras:  

- ✅ Cada clase y método incluye **comentarios** explicativos.  
- ✅ La **separación en archivos** facilita la lectura y mantenimiento.  
- ✅ Este **README.md** documenta la arquitectura, ejecución y finalidad del sistema.  

Ejemplo de documentación dentro del código (`ColaTareas.java`):  

```java
// Clase que implementa una cola de tareas (FIFO)
// Permite encolar y desencolar tareas en orden de llegada
public class ColaTareas {
    private Queue<Tarea> cola;

    public ColaTareas() {
        cola = new LinkedList<>();
    }

    // Agrega una tarea al final de la cola
    public void encolar(Tarea tarea) {
        cola.add(tarea);
    }

    // Elimina y retorna la primera tarea en la cola
    public Tarea desencolar() {
        return cola.poll();
    }
}
