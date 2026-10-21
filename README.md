# Quiroga_fabricio
utn dv122

---

## Alumno

**Nombre del alumno**: _[FABRICIO QUIROGA]_

## 📝 Descripción del Proyecto

Este proyecto es un sistema de gestión de pedidos para una empresa de suministros de oficina. 
Implementa conceptos de Programación Orientada a Objetos (POO) en Java, permitiendo la creación, gestión y cálculo de precios de distintos tipos de pedidos, 
con validaciones específicas mediante excepciones.

### Objetivos

- Crear un modelo orientado a objetos para la gestión de pedidos de oficina.
- Calcular precios finales basados en características específicas de cada tipo de pedido.
- Validar datos de entrada y asegurar la integridad de la información con excepciones específicas.

## 🛠️ Funcionalidades del Sistema

El sistema ofrece las siguientes funcionalidades:

### 1. Gestión de Pedidos

- **Pedido de Papel Mensual**: Permite gestionar pedidos de papel con una cantidad específica de resmas.
- **Pedido Electrónico**: Permite gestionar pedidos de servicios electrónicos, aplicando un porcentaje adicional sobre el monto base.

### 2. Cálculo de Precio Final

- **Pedido de Papel Mensual**: Calcula el precio final multiplicando el monto base por la cantidad de resmas.
- **Pedido Electrónico**: Calcula el precio final aplicando un porcentaje extra sobre el monto base.

### 3. Validaciones

- Manejo de excepciones para asegurar que la cantidad de resmas sea mayor a cero en los pedidos de papel.
- Validación de que el campo de motivo no esté vacío en los pedidos electrónicos.

### 4. Consultas y Listados

- Obtener un listado de todos los pedidos registrados.
- Buscar un pedido específico por su identificador único.
- Consultar pedidos electrónicos en función del motivo.

### 5. Cálculo Total General

- Calcular y retornar el monto total a pagar sumando los precios finales de todos los pedidos registrados.

## 📦 Estructura del Proyecto

El proyecto está compuesto por las siguientes clases y subclases:

### 1. **Pedido** (Clase Abstracta)

- **Atributos**:
    - `idPedido`: Identificador único y autoincremental del pedido.
    - `fechaCreacion`: Fecha en que se crea el pedido.
    - `montoBase`: Monto base del pedido.
- **Métodos Abstractos**:
    - `calcularPrecioFinal()`: Método abstracto para calcular el precio final del pedido, implementado en las subclases.

### 2. **PedidoPapelMensual** (Subclase de Pedido)

- **Atributos Específicos**:
    - `fechaEntrega`: Fecha de entrega del pedido.
    - `cantidadResmas`: Cantidad de resmas solicitadas (debe ser mayor a 0).
- **Métodos**:
    - `calcularPrecioFinal()`: Calcula el precio final multiplicando el monto base por la cantidad de resmas.

### 3. **PedidoElectronico** (Subclase de Pedido)

- **Atributos Específicos**:
    - `motivo`: Motivo del pedido (no puede estar vacío).
    - `porcentajeExtra`: Porcentaje adicional que se aplica sobre el monto base.
- **Métodos**:
    - `calcularPrecioFinal()`: Calcula el precio final aplicando el porcentaje extra al monto base.

### 4. **Sistema** (Clase Principal)

- **Atributos**:
    - `pedidos`: Lista de pedidos registrados en el sistema.
- **Métodos**:
    - `agregarPedidoPapelMensual(LocalDate fechaCreacion, double montoBase, LocalDate fechaEntrega, int cantidadResmas)`: Agrega un pedido de papel mensual y válida que la cantidad de resmas sea mayor a cero.
    - `agregarPedidoElectronico(LocalDate fechaCreacion, double montoBase, String motivo, double porcentajeExtra)`: Agrega un pedido electrónico y válida que el motivo no esté vacío.
    - `traerPedidos()`: Retorna la lista completa de pedidos.
    - `traerPedido(int idPedido)`: Retorna un pedido específico por su identificador.
    - `traerPedido(String motivo)`: Retorna una lista de pedidos que coinciden con el motivo ingresado.
    - `calcularTotalGeneral()`: Calcula y retorna el total a pagar de todos los pedidos en el sistema.
