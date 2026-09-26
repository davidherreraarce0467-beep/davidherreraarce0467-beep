# David Herrera Arce

Más de 25 años de trayectoria en informática, con proyectos entregados para instituciones de gobierno y empresas privadas de distintos rubros. Trabajo en paralelo con dos generaciones de tecnología: GenExus, desde sus primeras versiones hasta la 18, y un stack propio en Node.js/Express + SQL Server para los sistemas que construyo hoy. Diseño y entrego sistemas de gestión a medida (ERP, administración interna, punto de venta) de principio a fin: modelo de datos, lógica de negocio y despliegue en producción.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![GenExus](https://img.shields.io/badge/GenExus-hasta_v18-0057B7?style=flat)
![PM2](https://img.shields.io/badge/PM2-2B037A?style=flat&logo=pm2&logoColor=white)

Los proyectos abajo son sistemas en producción o en fase de revisión con datos reales de cada organización, así que los repositorios son privados. Cada uno describe qué resuelve y cómo está construido, sin exponer código ni datos de clientes.

---

## Proyectos destacados

### ERP multiempresa para pymes de servicios

ERP completo para empresas de construcción y servicios: control de proyectos con presupuesto y fondos, presupuestos detallados por partida con banco de precios reutilizable, CRM, compras y existencias con kardex y trazabilidad de lote, cuentas por pagar/cobrar con cheques, remuneraciones con cálculo legal chileno (liquidaciones y finiquitos), y generación de documentos PDF reales en el servidor. Multiempresa desde el diseño, con roles y permisos granulares por módulo.

- Backend Node.js/Express + SQL Server, frontend propio sin framework.
- Documentos oficiales (cotizaciones, órdenes de compra, liquidaciones) generados como PDF real server-side con Chromium headless, tamaño Carta.
- Panel de superadministrador para gestionar el ciclo de vida completo de cada empresa cliente (alta, módulos contratados, facturación de la suscripción).

**Estado:** en producción, uso real activo.

### Sistema administrativo para una compañía de bomberos

Sistema de gestión de Equipo de Protección Personal (EPP), tesorería y secretaría para un cuartel de bomberos. Cada asignación o retiro de equipo queda trazado de punta a punta: quién lo asignó, quién autorizó, y el propio bombero acepta o rechaza por correo con un enlace de un solo uso.

- Flujo de aprobación por correo con token de un solo uso, reutilizado también para cambios de cargo y entrega de reconocimientos.
- Módulo de tesorería: cuotas sociales, pagos, mora automática con recordatorio, comprobantes con numeración correlativa.
- Inventario serializado (una fila por elemento físico con código de barra), no por cantidades, porque el sistema necesita responder "de quién es este casco" en cualquier momento.

**Estado:** construido y desplegado, en fase de revisión con datos reales antes de pasar a uso operativo.

### Sistema de gestión de agua potable rural

Sistema para un comité de Agua Potable Rural (APR): registro de socios, lectura de medidores, generación de boletas, cortes de suministro por no pago, tarifas, caja y pagos, con facturación electrónica y pago en línea.

- Integración con Webpay/Transbank para pago en línea de boletas.
- Integración por SOAP con un servicio externo (facturación electrónica ante el SII).
- Módulo de cortes de suministro ligado al estado de pago de cada socio.

**Estado:** en producción.

### Sistema de gestión de beneficios sociales para un municipio

Backend para el área de desarrollo social de un municipio: registro de beneficiarios con su ficha social, tipos de beneficio y licitaciones que los financian, flujo de solicitud-aprobación-entrega, comprobantes firmables en PDF, y reportes/auditoría completos.

- Verificación de elegibilidad automática contra el tramo de registro social del beneficiario antes de aceptar una solicitud.
- Entregas con comprobante PDF y descarga protegida por token de un solo uso de corta duración, en vez de exponer el JWT de sesión en la URL.
- Auditoría de cada creación/edición/borrado (usuario, módulo, acción, IP) sin bloquear la respuesta al usuario.

**Estado:** en producción, uso real activo.

### Punto de venta para eventos con stock limitado

Punto de venta para instituciones que venden productos por cantidad fija en fechas puntuales (bazares, kermesses, almuerzos comunitarios): se arma el stock del día, varias cajas venden en paralelo contra ese mismo stock hasta agotarlo, y cada venta imprime un ticket.

- Reserva de stock en tiempo real por ítem al agregarlo al carrito, para que dos cajas nunca vendan la misma última unidad.
- Liberación automática de carritos abandonados (con aviso previo al cajero) para no dejar stock fantasma retenido.
- Helper de impresión local sin diálogo del navegador, para que cada caja imprima directo en su impresora térmica.

**Estado:** desplegado, primer evento real en preparación.

---

## Cómo trabajo

Node.js + Express + SQL Server como stack por defecto para este tipo de sistema (relacional, con integridad referencial y trazabilidad real, no un motor documental). Cada proyecto parte del modelo de datos y las reglas de negocio en stored procedures, con la lógica de validación repetida también en la capa de aplicación. Priorizo verificar cada cambio contra el sistema real antes de darlo por cerrado, no solo contra la lógica en el papel.

---

## Contacto

- Correo: [david.herrera.arce.0467@gmail.com](mailto:david.herrera.arce.0467@gmail.com)
- LinkedIn: [david-herrera-arce](https://www.linkedin.com/in/david-herrera-arce-04051621/)
