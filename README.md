# Guía de usuario de LINA Transcript

Documentación pública de la plataforma, publicada con [Mintlify](https://mintlify.com)
desde el proyecto **linatranscript** de la organización DOOLE HEALTH.

- Sitio: https://linatranscript.mintlify.app
- Dominio propio: `docs.linahealthtranscript.com`

## Ver los cambios en local

```bash
npm i -g mint
mint dev               # http://localhost:3000
```

Antes de hacer push:

```bash
mint validate          # build completo, en estricto
mint broken-links      # enlaces internos
```

## Publicar

No hay comando de despliegue. Mintlify observa este repositorio y **publica solo
al hacer push a `main`**.

Al añadir una página hay que darla de alta en `docs.json`: una página que no
está en `navigation` no aparece en el menú, aunque el fichero exista.

## Dos copias, y eso hay que resolverlo

Este contenido existe **también** en el repositorio del producto,
`DooleHealth/LinaTranscript-PyAnnoteAI`, en la carpeta `docs-site/`. Está ahí
porque es donde se escribió: verificando cada afirmación contra el código que
documenta.

Tener dos copias es una fuente de documentación desfasada. Conviene quedarse con
una:

- **Recomendado:** apuntar el proyecto de Mintlify a
  `DooleHealth/LinaTranscript-PyAnnoteAI`, rama `develop`, directorio
  `docs-site`, y archivar este repositorio. La documentación viaja con el código
  que describe, y queda dentro de la organización en lugar de en una cuenta
  personal.
- **Alternativa:** dejarlo aquí y borrar `docs-site/` del repositorio del
  producto. Más simple de operar, a cambio de que sea más fácil que la
  documentación se quede atrás cuando cambie la aplicación.

Mientras haya dos, cualquier cambio hay que hacerlo en las dos.

## Criterios de redacción

1. **Solo se documenta lo que existe en el código.** Nada de funciones
   prometidas ni de comportamiento supuesto.
2. **Se avisa de los límites.** La nota es un borrador, la identificación por
   exclusión es una deducción, el vocabulario no corrige nada. Documentar solo
   lo que funciona bien genera desconfianza en cuanto falla algo.
3. **Se escribe para quien está en consulta**, no para quien construye la
   plataforma. Nada de «diarización», «LLM» o «ASR» sin explicar.

## Relación con la guía en PDF

Parte de **Lina Transcript — Guía básica de uso, v1.0 (septiembre de 2026)**, en
castellano y catalán. Aquí está ampliada y corregida en tres puntos en los que
la aplicación ha cambiado desde que se escribió el PDF:

| Lo que dice el PDF | Lo que hace hoy la aplicación |
| --- | --- |
| «Configuración: solo lo cambia el propietario del centro» | Lo gestiona el proveedor del servicio. Ni el propietario del centro puede cambiarlo. |
| Ocho secciones en el menú lateral | Diez: se añadieron **Terminología** y **Plan y facturación**. |
| «Hay dos roles: propietario y miembro» | Tres: propietario, administrador y miembro. |

Si se reedita el PDF, conviene corregirlo allí también.

## Pendiente

- **Rehacer `images/inicio.png` y `images/configuracion.png`**: vienen del PDF y
  arrastran lo anterior —el menú con ocho secciones y la línea «Necesitas ser
  propietario de un centro para cambiar este ajuste»—. El texto dice lo
  correcto; las imágenes no.
- **Capturas que faltan**: grabación en curso con el estado de pausa, tarjeta de
  la nota con el aviso de revisión pendiente, y el comprobador de reglas de
  terminología.
- **Traducciones.** La plataforma está en español, catalán, inglés y chino; la
  documentación solo en español. Mintlify lo soporta con
  `navigation.languages` y un directorio por idioma. Conviene esperar a que la
  versión española esté estable.
- **IVA en la página de facturación.** No se afirma si los precios lo incluyen:
  el precio de Stripe está como `tax_behavior: exclusive` y eso no se cambia
  después de crearlo. Resolver primero en Stripe.
- **Enlace desde la aplicación** al sitio de documentación.
