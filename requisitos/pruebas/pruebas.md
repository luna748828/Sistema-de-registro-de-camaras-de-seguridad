# Casos de Prueba y Criterios de Aceptación

- **TC-01 (RF-01):** Validar registro con campos obligatorios llenos (Exitoso), sin campos opcionales (Alternativo) y con campo obligatorio vacío mostrando error específico (Error).
- **TC-02 (RF-02):** Validar reporte rápido con GPS activo (Exitoso), sin permiso GPS (Alternativo) y sin fotografía adjunta (Error).
- **TC-03 (RF-03):** Validar filtrado por barrio/tipo/estado con resultados (Exitoso), sin filtros (Alternativo) y sin coincidencias mostrando alerta (Error).
- **TC-04 (RF-04):** Validar visualización de marcador en mapa Leaflet y despliegue de datos al hacer clic.
- **TC-05 (RF-05):** Validar edición/eliminación de reporte propio con sesión iniciada y bloqueo al intentar editar reporte ajeno.
- **TC-06 (RNF-01):** Validar visualización responsive en pantalla móvil y escritorio.
- **TC-07 (RNF-02):** Validar restricción de escritura en Supabase mediante políticas RLS.
- **TC-08 (RNF-03):** Medir tiempo de respuesta de consulta y filtrado (< 3 segundos).
