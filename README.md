# app_colectivos

## Colectivos

Aplicación web/PWA de transporte público para CABA y AMBA. El objetivo es indicar qué vehículos tienen posición GPS, qué datos son predicciones y qué alternativas convienen según el criterio de cada persona.

### Primera versión publicada

- mapa libre con OpenStreetMap;
- marcador con figura de colectivo para vehículos con GPS reciente;
- marcadores diferenciados para trenes, subtes y datos programados;
- filtros por modo de transporte;
- búsqueda de Estación Lanús a UADE Independencia, Lima 775;
- orden por tiempo, precio, caminata o transbordos;
- perfiles SUBE y cantidad mensual de viajes de subte;
- tarjetas de alternativas y estado de frescura del dato;
- uso anónimo, sin registro.

La versión publicada funciona actualmente en modo demo. Las tarifas están marcadas como estimaciones y los vehículos de ejemplo se mueven para validar la interfaz. La app no mostrará GPS como real hasta validar la posición recibida desde una fuente oficial.

### Tiempo real

La integración prevista usa feeds GTFS estáticos y GTFS-Realtime desde el backend, con cache y timestamp de cada actualización. El navegador nunca debe recibir tokens de proveedor. Cuando una fuente no entregue posición, la interfaz mostrará horario programado o predicción.

Fuentes y referencias:

- API Transporte CABA: https://datosabiertos-apis.buenosaires.gob.ar/BA_Root/Documentacion?schema_name=Transporte_3
- Registro de API Transporte: https://api-transporte.buenosaires.gob.ar/registro
- Buenas prácticas GTFS-Realtime: https://gtfs.org/es/documentation/realtime/realtime-best-practices/
- OpenTripPlanner: https://docs.opentripplanner.org/
- OpenStreetMap: https://www.openstreetmap.org/copyright

### Prueba inicial

Origen: Estación Lanús.
Destino: UADE Independencia, Lima 775.
Horario: próximo día hábil, 07:00, America/Argentina/Buenos_Aires.

### Deploy

Producción: https://appcolectivos-seven.vercel.app

El próximo paso es auditar la cobertura real de AMBA, incorporar el token oficial en variables privadas de Vercel y reemplazar el dataset demo por un recolector persistente.
