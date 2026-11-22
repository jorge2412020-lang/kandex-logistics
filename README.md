# KANDEX LOGISTICS — Web 0.3.0

Aplicación de Logística enfocada en computadora. Abre directamente en https://jorge2412020-lang.github.io/kandex-logistics/ y guarda el catálogo en ese navegador, sin enviar materiales o fotografías a GitHub. La versión instalable para PC se evaluará después de validar esta web.

## Novedades
- **Mi almacén:** plano superior con racks que se pueden mover, girar, renombrar y dimensionar. Modo Consulta y modo Edición; guardar/cancelar distribución. Evita superposiciones.
- **Vista frontal:** configura posiciones por nivel, por ejemplo `4,4,4` para tres niveles de cuatro materiales. Hasta 20 niveles y 30 posiciones por nivel, 200 racks.
- **Capacidad real:** muestra posiciones ocupadas, disponibles y rack lleno. Una posición admite un material distinto; no es cantidad de piezas ni capacidad de carga/peso.
- **Proyectos:** registra varios proyectos separados por coma (Volvo, Rivian, BMW). Filtra el plano y las posiciones; la disponibilidad siempre considera todos los proyectos.
- **Asignación y reubicación:** selecciona una posición libre, busca el material y asígnalo. Reubicar actualiza la ficha y libera el origen en una sola transacción. No admite doble ocupación ni reducir/eliminar posiciones ocupadas.
- **Sin ubicación en el plano:** lista los materiales todavía no vinculados. Las ubicaciones antiguas escritas a mano se conservan y no se interpretan automáticamente al crear un rack. Revisa y vincula cada material a su posición; elimina una ubicación manual antigua desde su ficha si ya no aplica.
- **Ficha imprimible:** fotografía principal, parte, nombre, características, proyectos, ubicaciones, datos opcionales y actualización. Vista previa blanca, tamaño carta y opción de PDF en el diálogo del navegador. Los textos largos pueden ocupar más de una hoja.
- **Respaldo completo JSON v2:** materiales, fotos, proyectos, plano, niveles, capacidades y asignaciones. Recupera también los respaldos web anteriores v1 (sin plano). Antes de reemplazar los datos muestra fecha y cantidades y solicita descargar un respaldo previo.

## Catálogo
Registro y edición, hasta 20 fotos por material, búsqueda, filtros, páginas de 20 y miniaturas. Fotografías optimizadas a 1600 px; conserva los originales por separado. Seis materiales ficticios opcionales.

## Actualización y conservación de datos
Se mantiene el nombre de la base IndexedDB y se migra de versión 1 a 2 sin borrar materiales ni fotografías. Abre la misma URL en el mismo navegador. Si otra pestaña bloquea la actualización, ciérrala y recarga. Antes de una actualización importante crea un respaldo.

No hay servidor compartido ni sincronización entre computadoras. Usa una computadora principal y exporta/importa el respaldo para trasladar información. Importar reemplaza el catálogo y el plano del destino. Los respaldos web no son compatibles con los ZIP de la versión Python anterior.

Los datos dependen del almacenamiento disponible del navegador. Borrar datos del sitio o usar modo privado puede eliminarlos. Importación de respaldo limitada a 200 MB; el número de materiales que cabe depende también del tamaño de las fotos. No se ha validado un catálogo real de 1,500 fotos de gran tamaño. La caché permite abrir la app sin conexión tras una visita completada; no sustituye un respaldo.

## Código y pruebas
HTML, CSS y JavaScript sin dependencias externas. El `index.html` publicado contiene la aplicación y el logo integrados; `sw.js` gestiona la caché local. Los cambios de ubicación se validan contra datos recientes en una transacción IndexedDB, incluida la ocupación entre pestañas.

Validación automatizada del modelo con 1,500 registros ficticios, capacidades, colisiones, asignaciones, reubicación, filtros, compatibilidad de ubicaciones manuales y serialización del respaldo. Las pruebas no representan certificación para uso industrial.
