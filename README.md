# Calculadora Profesional para Revendedores v4.0
### Manual de Operación · Guía de Despliegue · Plantilla de Duplicación

> **Desarrollador:** Landirianos Site | **CEO Fundador:** Terry Romero | **Contacto:** landirianositeoficial@gmail.com

---

## Descripción General

Software de cotización profesional multicambiario diseñado para revendedores de prendas. Opera como **Single Page Application (SPA)** de archivo único, sin dependencias de servidor, frameworks ni instalaciones adicionales. Compatible con cualquier navegador web moderno.

**Motor de cálculo:** Reactivo en tiempo real  
**Divisas soportadas:** USD / EUR / Bolívares (Bs.) — tres tasas paralelas  
**Modo de uso:** Apertura directa del archivo `index.html` en el navegador  

---

PRUEBA LA CALCULADORA AQUI: https://n9.cl/8cxae

## Inicio Rápido

```
1. Localiza el archivo:  index.html
2. Haz doble clic sobre él — se abre en tu navegador predeterminado
3. Actualiza las tasas cambiarias en el Panel Cambiario
4. Edita los precios de tu proveedor en la Tabla de Productos (si es necesario)
5. Agrega filas de cotización y configura cada prenda
6. Lee los resultados en el Tablero Contable inferior
```

---

## Estructura del Archivo

```
Calculadora Profesional para Revendedores/
├── index.html     ← Aplicación completa (HTML + CSS + JS)
├── BITACORA.txt   ← Registro técnico de versiones
└── README.md      ← Este archivo
```

---

## Panel Cambiario

| Campo | Descripción | Fuente Recomendada |
|---|---|---|
| **Tasa Oficial USD** | Bolívares por 1 USD (BCV) | bcv.org.ve |
| **Tasa Oficial EUR** | Bolívares por 1 EUR (BCV) | bcv.org.ve |
| **Tasa Binance P2P** | Bolívares por 1 USDT (mercado P2P) | p2p.binance.com |

> Actualiza estas tasas cada vez que abras la calculadora. Los resultados del tablero reflejan las tres conversiones de forma simultánea e instantánea.

---

## Tabla de Precios Base — Edición Segura

La tabla editable es la **única fuente de verdad** del motor de cálculo. Para modificarla:

1. Haz clic en cualquier celda de **Proveedor**, **Detal** o **Mayor**
2. Escribe el nuevo valor en USD (usa punto como separador decimal, ej: `3.50`)
3. Presiona **Tab** o **Enter** — el recálculo es automático e instantáneo

### Columnas de la tabla

| Columna | Color | Significado |
|---|---|---|
| **Proveedor** | Rojo | Costo que tú pagas al taller/fabricante |
| **Detal** | Verde | Precio de venta unitaria a un solo cliente |
| **Mayor** | Azul | Precio de venta por volumen |

### Productos incluidos por defecto

| # | Producto | Proveedor | Detal | Mayor |
|---|---|---|---|---|
| 1 | Unicolor | $2.96 | $5.00 | $2.96 |
| 2 | Sublimado Catálogo | $4.20 | $6.00 | $4.20 |
| 3 | Sublimado Personalizado | $4.90 | $6.50 | $4.90 |
| 4 | 2XXL/3XXL Unicolor | $4.50 | $5.50 | $5.50 |
| 5 | 2XXL/3XXL Sublimado Catálogo | $5.90 | $7.00 | $5.90 |
| 6 | 2XXL/3XXL Sublimado Personalizado | $6.80 | $8.00 | $6.80 |
| 7 | Microdurazno con DTF Catálogo | $6.34 | $7.00 | $6.34 |
| 8 | Microdurazno con DTF Personalizado | $6.34 | $7.00 | $6.34 |
| 9 | Unicolor / Algodón | $7.40 | $8.00 | $7.40 |

---

## Panel de Cotización

### Filas Dinámicas

- **+ Agregar Fila:** Añade una nueva prenda a la cotización
- **⧉ Clonar:** Duplica la fila con los mismos parámetros
- **✕ Eliminar:** Remueve la fila de la cotización
- Puedes mezclar productos distintos en la misma cotización

### Módulo de Promociones

> ⚠️ Las promociones afectan **solo los ingresos del revendedor**. El costo al proveedor permanece intacto.

| Modo | Funcionamiento |
|---|---|
| **% Descuento** | Reduce el monto cobrado al cliente en el porcentaje indicado (0–100%) |
| **$ Precio Fijo** | Establece un precio unitario fijo para toda la cotización |

### Logística de Entrega

| Opción | Costo | Comportamiento |
|---|---|---|
| Pickup en Tienda | $0.00 | Sin cargo adicional |
| Entrega en la Avenida | $1.00 fijo | Se suma al cobro del cliente |
| Delivery a Domicilio | Variable | Ingresa el monto según distancia |

> El delivery es un **pass-through**: se cobra al cliente pero **no afecta el margen de ganancia** del revendedor.

### Diseños Adicionales

| Tipo | Costo por prenda |
|---|---|
| Diseño de Catálogo | +$0.60 USD/unidad |
| Diseño Personalizado | +$0.75 USD/unidad |

Ambos valores se **multiplican por la cantidad total de prendas** de toda la cotización.

---

## Tablero Contable — Resultados

| # | Tarjeta | Fórmula |
|---|---|---|
| ① | **Monto al Proveedor** | Σ(costo_proveedor × cantidad) |
| ② | **Ganancia Revendedor** | Cobro_cliente − Costo_proveedor |
| ③ | **Monto del Cliente** | Subtotal prendas ± promo |
| ④ | **+ Delivery** | ③ + costo de entrega |
| ⑤ | **Gran Total** | ④ + diseños adicionales |

Cada tarjeta muestra el monto en **USD** y su equivalencia en **Bs.** bajo las tres tasas configuradas.

### Formato de Bolívares

```
Separador de miles   →  Punto   (.)
Separador decimal    →  Coma    (,)
Ejemplo              →  1.250,75 Bs.
```

---

## Botón "Borrar y Reiniciar"

Restablece todos los campos dinámicos a cero sin recargar el navegador:
- Elimina todas las filas de cotización
- Desactiva módulo de promociones
- Resetea delivery a "Pickup en Tienda"
- Limpia diseños adicionales

> **Los precios base de la tabla de productos se conservan** tras el reset.

---

## Guía de Duplicación para Nuevos Negocios

Para adaptar este software a otro negocio:

### 1. Personalizar Nombre y Colores

Abre `index.html` en un editor de texto (Notepad++, VS Code). Modifica:

```css
/* Cambiar colores en :root */
--accent: #D35400;        /* Color acento principal */
--bg: #111111;            /* Fondo */
--card: #1C1C1C;          /* Fondo de tarjetas */
```

```html
<!-- Cambiar nombre en el header -->
<h1>Calculadora Profesional para Revendedores</h1>
```

### 2. Cambiar Productos

Localiza el arreglo `DEFAULT_PRODUCTS` en el bloque `<script>` y edita los valores:

```javascript
const DEFAULT_PRODUCTS = [
  {name:'Nombre Producto', prov:0.00, detal:0.00, mayor:0.00},
  // ... agrega o elimina objetos según tu catálogo
];
```

### 3. Cambiar Costos de Diseños

```javascript
// En la función recalc():
const designExtra = (dCatalog * 0.60 + dCustom * 0.75) * totalQty;
//                             ^^^^              ^^^^
//                         Costo catálogo   Costo personalizado
```

### 4. Cambiar Costo de Entrega en Avenida

```javascript
// En la función getDeliveryCost():
if(type==='avenida') return 1.00;  // Cambia 1.00 por tu valor
```

---

## Requisitos de Sistema

| Requisito | Especificación |
|---|---|
| Navegador | Chrome 90+ / Firefox 88+ / Edge 90+ |
| Conexión a internet | Solo para cargar tipografía Google Fonts |
| Servidor web | No requerido |
| Instalación | No requerida |
| Base de datos | No requerida |

---

## Notas de Mantenimiento

- **Los precios base no se guardan** entre sesiones. Si los modificas en la tabla, deberás editarlos también en el arreglo `DEFAULT_PRODUCTS` del código para que persistan.
- **Las tasas cambiarias** deben actualizarse manualmente en cada sesión de trabajo.
- Para guardar una cotización, usa la función de impresión del navegador (`Ctrl+P`) o exporta a PDF.

---

*Calculadora Profesional para Revendedores v4.0 — Marca Blanca — Motor Multicambiario*

© 2026 Landirianos Site. Todos los derechos reservados. Queda prohibida la reproducción, distribución o modificación comercial de este software sin autorización expresa del autor.
