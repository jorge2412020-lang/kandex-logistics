# KANDEX LOGISTICS — Web

Catálogo visual de materiales de almacén. La página abre directamente la aplicación, sin instalar Python ni ejecutar el programa de Windows.

## Funciones
- Registro y edición con varias fotos y ubicaciones.
- Búsqueda por número de parte, nombre o características.
- Categorías y ubicaciones como filtros.
- Páginas de 20 materiales y miniaturas para catálogos grandes.
- Fotos optimizadas a un máximo de 1600 px; hasta 20 por material.
- Datos locales en IndexedDB: no se envían materiales ni fotos a GitHub.
- Exportación y restauración mediante JSON (hasta 200 MB por archivo para importar).
- Seis ejemplos ficticios opcionales, con ilustraciones.
- Caché sin conexión después de la primera visita completada.

## Uso y límites
El catálogo pertenece a este navegador, dispositivo y dirección del sitio. Borrar datos de navegación, usar modo privado o cambiar de dirección puede hacerlo inaccesible o eliminarlo. Exporta respaldos regularmente. No hay sincronización, servidor compartido, autenticación ni control de inventario. Los respaldos JSON web son independientes de los ZIP de la app Windows. Guarda originales de tus fotografías por separado.

No se incluyen materiales reales ni datos empresariales.

## Publicar
GitHub Pages: Settings → Pages → Deploy from a branch → main → /(root) → Save.

## Desarrollo
HTML, CSS y JavaScript sin dependencias externas. Servir mediante HTTP local o HTTPS; IndexedDB y service workers dependen del navegador. El sitio público distribuye la aplicación; cada visitante conserva su propio catálogo local.
