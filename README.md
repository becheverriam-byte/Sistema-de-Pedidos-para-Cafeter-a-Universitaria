# Sistema de Pedidos para Cafetería Universitaria

## Descripción del Caso
Sistema de gestión de pedidos diseñado para optimizar el servicio de la cafetería universitaria durante horas pico. Permite registrar, procesar y gestionar órdenes de alimentos y bebidas de manera eficiente, sincronizando la recepción de pedidos con su preparación.

## Objetivos
- Automatizar el proceso completo de gestión de pedidos
- Reducir tiempos de atención durante periodos de alta demanda
- Garantizar precisión en cálculos financieros y transiciones de estado
- Proporcionar información en tiempo real sobre disponibilidad de productos

## Alcance
**Incluye:**
- Registro de órdenes con múltiples productos
- Cálculo automático de totales e impuestos
- Gestión del estado de pedidos (pendiente → en preparación → terminado → entregado)
- Consulta de productos disponibles en tiempo real
- Generación de comprobantes de venta

**Excluye:**
- Gestión de inventario
- Control de proveedores
- Administración de empleados
- Sistema de puntos o lealtad

## Requerimientos Funcionales

| ID | Requerimiento | Tipo | Descripción |
|----|---------------|------|-------------|
| RF-01 | Registrar pedido | Esencial | Registrar nuevo pedido validando productos en menú |
| RF-02 | Calcular total | Esencial | Calcular subtotal, impuesto 10% y total con precisión decimal |
| RF-03 | Gestionar estado | Esencial | Controlar transiciones de estado con timestamp |
| RF-04 | Consultar menú | Condicional | Mostrar productos disponibles con filtros por categoría |
| RF-05 | Generar comprobante | Opcional | Comprobante con detalles completos del pedido |

## Requerimientos No Funcionales

| ID | Requerimiento | Tipo | Descripción |
|----|---------------|------|-------------|
| RNF-01 | Rendimiento | Desempeño | Procesar pedido en <10s, consultas menú <3s |
| RNF-02 | Confiabilidad | Fiabilidad | 99% disponibilidad (7:00 am - 7:00 pm) |
| RNF-03 | Usabilidad | Usabilidad | Registrar pedido en 3 clics máximo |

## Tabla de Pruebas

| ID Prueba | Requerimiento | Datos Entrada | Resultado Esperado | Estado |
|-----------|---------------|---------------|-------------------|---------|
| PU-01 | RF-01 | Café($2), Sandwich($5) | Pedido registrado, subtotal $7 | ✔ PASÓ |
| PU-02 | RF-02 | Subtotal: $15 | Total: $16.50, impuesto: $1.50 | ✔ PASÓ |
| PU-03 | RF-03 | P001 → "en preparación" | Estado actualizado, timestamp | ✔ PASÓ |
| PV-01 | RF-01 + RF-02 | Café x2, Jugo x1 | Subtotal $7, total $7.70 | ✔ PASÓ |
| PV-02 | RF-03 + RF-04 | Cambio estado + consulta | Estado actualizado, menú actual | ✔ PASÓ |

## Propuesta de Mantenimiento

### Mantenimiento Correctivo
- **RF-02**: Corregir errores de redondeo en cálculos
- **RF-03**: Validar transiciones de estado inválidas
- **RF-04**: Sincronizar menú en tiempo real (<30s)

### Mantenimiento Adaptativo
- **RF-02**: Adaptar a nuevo impuesto (10% → 12%)
- **RNF-02**: Extender horario (7:00 am - 9:00 pm)
- **Sistema**: Integrar nuevas pasarelas de pago

### Mantenimiento Perfectivo
- **RNF-03**: Reducir clics de 3 a 2 por pedido
- **RNF-01**: Optimizar tiempo de procesamiento (10s → 5s)
- **RF-04**: Implementar búsqueda predictiva

## Reflexión sobre Control de Versiones

El control de versiones es fundamental para gestionar las diferentes fases de mantenimiento propuestas. Se recomienda:

### Estrategia de Ramificación
- **main**: Versiones estables en producción
- **develop**: Integración de nuevas funcionalidades
- **feature/**: Desarrollo de mejoras perfectivas
- **hotfix/**: Correcciones urgentes
- **release/**: Preparación de adaptaciones

### Versionado Semántico
Utilizar formato `MAJOR.MINOR.PATCH` donde:
- **MAJOR**: Cambios adaptativos que rompen compatibilidad
- **MINOR**: Mejoras perfectivas con compatibilidad hacia atrás
- **PATCH**: Correcciones correctivas

### Gestión de Configuraciones
- Parametrizar valores variables (impuestos, horarios)
- Mantener scripts de migración de base de datos
- Documentar cambios entre versiones
- Automatizar procesos de despliegue

### Beneficios Implementados
- Trazabilidad de cambios específicos por tipo de mantenimiento
- Rollback rápido en caso de problemas con correcciones
- Desarrollo paralelo de adaptaciones y mejoras
- Documentación automática de evoluciones del sistema

## Conclusión
El sistema requiere un enfoque balanceado de mantenimiento donde las correcciones aseguren estabilidad operativa, las adaptaciones mantengan relevancia ante cambios externos, y las mejoras perfectivas optimicen continuamente la experiencia de usuario. El control de versiones robusto permite gestionar esta evolución de manera ordenada y documentada.