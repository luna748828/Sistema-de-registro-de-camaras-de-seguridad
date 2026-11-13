# Inventario de Requerimientos del Proyecto

## Requerimientos Funcionales

### RF-01: Registro de cámaras
- **Descripción:** El sistema permitirá registrar cámaras de seguridad mediante un formulario que solicite obligatoriamente dirección o punto de referencia, barrio, tipo y estado de la cámara. Los campos opcionales podrán dejarse vacíos y el sistema impedirá el registro si falta un dato obligatorio, mostrando un mensaje específico. No requiere iniciar sesión (se guarda como Anónimo).
- **Versión:** 1.2
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Validado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given que el usuario ingresa dirección, barrio, tipo y estado; When presiona "Guardar reporte"; Then el sistema almacena el registro y muestra confirmación. Si falta un campo obligatorio, bloquea el envío e indica el campo pendiente.

### RF-02: Reporte rápido
- **Descripción:** El sistema permitirá generar un reporte rápido mediante una fotografía y la ubicación geográfica disponible, permitiendo registrar la cámara aunque no se obtengan coordenadas.
- **Versión:** 1.0
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given que el usuario toma o adjunta una foto; When la envía sin GPS activo; Then el sistema guarda el reporte sin coordenadas y notifica el registro.

### RF-03: Consulta y filtrado
- **Descripción:** El sistema permitirá consultar las cámaras registradas y filtrarlas por barrio, tipo y estado, mostrando "No se encontraron cámaras con los filtros seleccionados" si no hay coincidencias.
- **Versión:** 1.0
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given que existen registros; When el usuario aplica filtros sin coincidencias; Then se muestra el mensaje de alerta correspondiente.

### RF-04: Visualización en mapa
- **Descripción:** El sistema permitirá visualizar en un mapa (Leaflet/OpenStreetMap) las cámaras con coordenadas y consultar su información al seleccionar el marcador.
- **Versión:** 1.0
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given una cámara con coordenadas; When el usuario hace clic en su marcador en el mapa; Then se despliega su dirección, tipo y estado.

### RF-05: Cuenta y gestión de reportes propios
- **Descripción:** El sistema permitirá crear cuenta, iniciar sesión y editar o eliminar únicamente los reportes asociados a dicha cuenta.
- **Versión:** 1.1
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given un usuario autenticado; When intenta editar un reporte de otro usuario; Then el sistema bloquea la acción por políticas RLS.

---

## Requerimientos No Funcionales

### RNF-01: Diseño adaptable
- **Descripción:** La interfaz deberá adaptarse a pantallas de dispositivos móviles y computadores manteniendo su funcionalidad.
- **Versión:** 1.0
- **Prioridad:** Media
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given el acceso desde móvil o PC; When se renderiza la interfaz; Then todos los botones y formularios son legibles y funcionales.

### RNF-02: Control de permisos y seguridad
- **Descripción:** El sistema restringirá la edición y eliminación de reportes al propietario autenticado mediante políticas RLS en Supabase.
- **Versión:** 1.1
- **Prioridad:** Alta
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Implementado
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given una petición de modificación; When el `user_id` no coincide con el autor; Then Supabase rechaza la operación.

### RNF-03: Tiempo de respuesta
- **Descripción:** El sistema responderá las consultas y filtrados en un tiempo máximo de 3 segundos bajo condiciones normales de uso.
- **Versión:** 1.0
- **Prioridad:** Media
- **Responsable:** Luna Acosta / Jillian Caicedo
- **Estado:** Por validar
- **Fecha:** 12/11/2026
- **Criterio de aceptación:** Given una consulta a la base de datos; When se aplica un filtro; Then los resultados cargan en <= 3 segundos.
