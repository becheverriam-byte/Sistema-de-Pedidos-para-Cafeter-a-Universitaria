# Propuesta de Mantenimiento - Sistema de Pedidos para Cafetería

## Requerimientos Funcionales

### RF-01 Registrar pedido (Esencial)
- Registrar nuevo pedido con múltiples productos
- Validar existencia de productos en menú
- Capturar identificador único, fecha, hora, cajero responsable

### RF-02 Calcular total (Esencial)
- Calcular subtotal sumando valores de productos
- Aplicar impuesto del 10%
- Mostrar total final con precisión decimal de dos dígitos

### RF-03 Gestionar estado pedido (Esencial)
- Controlar transiciones entre estados: pendiente → en preparación → terminado → entregado
- Registrar timestamp de cada cambio de estado

### RF-04 Consultar menú disponible (Condicional)
- Mostrar productos disponibles en tiempo real
- Indicar productos agotados temporalmente
- Permitir filtros por categorías (bebidas, alimentos, snacks)

### RF-05 Generar comprobante (Opcional)
- Generar comprobante de venta legible
- Incluir identificador, fecha, productos, precios, subtotal, impuesto, total y cajero

## Requerimientos No Funcionales

### RNF-01 Rendimiento (Desempeño)
- Procesar registro de pedido estándar (hasta 5 productos) en menos de 10 segundos
- Tiempo de respuesta para consultas de menú no mayor a 3 segundos

### RNF-02 Confiabilidad (Fiabilidad)
- Mantener disponibilidad del 99% durante horario de cafetería (7:00 am - 7:00 pm)
- Recuperación de datos sin pérdida de información en caso de fallos

### RNF-03 Usabilidad (Usabilidad)
- Interfaz intuitiva que permita registrar pedido completo en máximo 3 clics
- Navegación entre funciones principales en máximo 2 clics
- Capacitación requerida: 30 minutos para cajero novato

## Propuestas de Mantenimiento por Caso de Uso

### Mantenimiento Correctivo

#### Caso: RF-02 Calcular total
- **Problema:** Errores de redondeo en cálculos con impuestos
- **Acción:** Revisar algoritmos aritméticos e implementar funciones con precisión decimal exacta
- **Prioridad:** Alta - impacta transacciones financieras

#### Caso: RF-03 Gestionar estado pedido
- **Problema:** Transiciones de estado inválidas permitidas
- **Acción:** Implementar validación estricta de flujo de estados y bloquear secuencias incorrectas
- **Prioridad:** Media - afecta integridad del proceso

#### Caso: RF-04 Consultar menú disponible
- **Problema:** Menú no se actualiza en tiempo real mostrando productos agotados
- **Acción:** Mejorar sincronización y garantizar actualización dentro de 30 segundos post-deshabilitación
- **Prioridad:** Media - impacta experiencia de usuario

### Mantenimiento Adaptativo

#### Caso: RF-02 Calcular total
- **Cambio:** Nueva tasa de impuesto del 12% en lugar del 10%
- **Acción:** Parametrizar porcentaje de impuesto y hacerlo configurable
- **Timeline:** 2 semanas - requerimiento legal

#### Caso: RNF-02 Confiabilidad
- **Cambio:** Extensión de horario de cafetería de 7:00 pm a 9:00 pm
- **Acción:** Ajustar requisitos de disponibilidad y ventanas de mantenimiento
- **Timeline:** 1 semana - cambio operativo

#### Caso: Sistema de pagos
- **Cambio:** Integración con nueva pasarela de pago electrónico
- **Acción:** Diseñar arquitectura modular para múltiples proveedores de pago
- **Timeline:** 4 semanas - expansión de servicios

### Mantenimiento Perfectivo

#### Caso: RF-01 Registrar pedido + RNF-03 Usabilidad
- **Mejora:** Reducir número de clics de 3 a 2 para registro completo
- **Acción:** Rediseñar interfaz con componentes más intuitivos y atajos de teclado
- **Beneficio:** 33% de mejora en velocidad de registro

#### Caso: RF-04 Consultar menú disponible
- **Mejora:** Implementar búsqueda predictiva y filtros múltiples
- **Acción:** Agregar búsqueda por nombre, categoría, ingredientes y filtros combinados
- **Beneficio:** 50% de mejora en eficiencia de consultas

#### Caso: RNF-01 Rendimiento
- **Mejora:** Reducir tiempo de procesamiento de 10s a 5s
- **Acción:** Implementar caching de menú frecuente y optimizar consultas a base de datos
- **Beneficio:** 100% de mejora en capacidad de procesamiento

## Plan de Implementación

### Fase 1 - Correctivo (Mes 1)
- Corrección de cálculos financieros (RF-02)
- Validación de transiciones de estado (RF-03)
- Sincronización de menú en tiempo real (RF-04)

### Fase 2 - Adaptativo (Mes 2)
- Parametrización de impuestos (RF-02)
- Extensión de horario operativo (RNF-02)
- Preparación para integración de pagos

### Fase 3 - Perfectivo (Mes 3)
- Optimización de interfaz de usuario (RNF-03)
- Mejora en sistema de búsqueda (RF-04)
- Optimización de rendimiento (RNF-01)

## Criterios de Aceptación

1. Sistema registra correctamente el 100% de pedidos con hasta 10 productos diferentes
2. Cálculos mantienen precisión del 100% sin errores de redondeo
3. Transiciones de estado siguen secuencia definida sin cambios inválidos
4. Consulta de disponibilidad refleja estado actual con actualización en 30 segundos
5. Comprobantes incluyen toda información requerida de manera legible y estructurada