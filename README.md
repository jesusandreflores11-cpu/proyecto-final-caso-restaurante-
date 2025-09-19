#  Proyecto Final - Estructura de Datos  
**Materia:** Estructura de datos  
**Alumnos:** [jesus andre flores garcia,jesus roberto,jordan rykelme,]  
**Profesor:** []  
**Fecha:** [septiembre 2025]  

---

 Descripción General
Este proyecto implementa un sistema de **gestión de pedidos para un restaurante de hamburguesas**, desarrollado en **Java**.  

Se utilizan **estructuras de datos avanzadas (listas, pilas, colas y colas de prioridad)** para organizar y procesar las órdenes de clientes de forma eficiente.  
Además, el sistema cuenta con una **interfaz gráfica (GUI)** para facilitar la interacción del usuario.  

---

##  Caso de Uso: Restaurante de Hamburguesas  

Un **restaurante de hamburguesas** recibe constantemente pedidos. El sistema organiza las órdenes de los clientes y las envía a cocina en el orden más eficiente posible.  

###  Escenario General
1. Los clientes llegan y ordenan hamburguesas, papas, bebidas y combos.  
2. Cada orden se convierte en una **tarea** dentro del sistema.  
3. El restaurante debe decidir **cómo procesar cada tarea**:  
   - **ColaTareas (FIFO):** las órdenes se atienden en orden de llegada.  
   - **PilaTareas (LIFO):** la última orden ingresada se procesa primero (ejemplo: cuando un cocinero se especializa en pedidos rápidos).  
   - **ColaPrioridades:** si llega un pedido **VIP o urgente**, se procesa antes que las demás.  
4. Todas las órdenes (procesadas o no) se almacenan en una **ListaTareas** para el control y seguimiento.  

###  Ejemplo de Pedidos
- Cliente 1:  Hamburguesa sencilla +  papas.  
- Cliente 2:  Doble hamburguesa +  refresco.  
- Cliente 3:  Hamburguesa con queso (URGENTE VIP).  
- Cliente 4:  Combo familiar (3 hamburguesas + 3 bebidas + 2 papas).  

###  Flujo con estructuras
- **Cola FIFO:**  
  - Orden de atención → Cliente 1 → Cliente 2 → Cliente 3 → Cliente 4.  
- **Cola de Prioridad:**  
  - El pedido del Cliente 3 (VIP) se atiende primero, luego siguen los demás.  
- **Pila LIFO:**  
  - El último pedido (Cliente 4) se atiende antes que los anteriores.  
- **Lista de Tareas:**  
  - Se guardan todos los pedidos, sin importar el orden de ejecución.  

 Gracias a este modelo, el restaurante puede **adaptarse a diferentes escenarios de atención**, garantizando rapidez y flexibilidad.  

---

##  1. Implementación de estructuras  
Se utilizaron las siguientes clases para cumplir con los requisitos del sistema:  

- **ListaTareas.java** → Maneja todas las órdenes en una lista dinámica.  
- **PilaTareas.java** → Procesa tareas en orden LIFO.  
- **ColaTareas.java** → Procesa tareas en orden FIFO.  
- **ColaPrioridades.java** → Atiende primero las órdenes más importantes.  
- **Empleado.java** y **Tarea.java** → Modelan la información de los empleados y pedidos.  
- **RestauranteAppGUI.java** → Proporciona una interfaz gráfica para interactuar con el sistema.  
- **Main.java** y **RestaurantePro.java** → Controlan la ejecución principal.  

---

##  2. Claridad y documentación  
- El código incluye **comentarios explicativos** en las clases y métodos.  
- La separación en **archivos independientes** facilita la comprensión.  
- Este **README.md** documenta el caso de uso, estructuras y ejecución del sistema.  

Ejemplo (`ColaTareas.java`):  

```java
// Cola de tareas (FIFO)
// Permite encolar pedidos en orden de llegada
public class ColaTareas {
    private Queue<Tarea> cola;

    public ColaTareas() {
        cola = new LinkedList<>();
    }

    // Agregar pedido a la cola
    public void encolar(Tarea tarea) {
        cola.add(tarea);
    }

    // Procesar el primer pedido en la cola
    public Tarea desencolar() {
        return cola.poll();
    }
}

3. Eficiencia del sistema

El sistema optimiza la gestión de pedidos:

Cola de Prioridades → Los pedidos VIP/urgentes se atienden antes que los demás.

Colas y Pilas → Permiten gestionar diferentes escenarios de cocina (FIFO para orden normal, LIFO para pedidos rápidos).

Lista de Tareas → Mantiene registro de todas las órdenes, útil para administración.

GUI → Mejora la interacción del usuario al visualizar pedidos en pantalla.

Ejemplo (ColaPrioridades.java):

// Cola de prioridad: primero se atienden pedidos VIP o urgentes
PriorityQueue<Tarea> colaPrioridad = new PriorityQueue<>(
    (t1, t2) -> Integer.compare(t2.getPrioridad(), t1.getPrioridad())
);
