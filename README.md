# mezcla-web

Sitio estático que sirve las dos URL públicas que exigen App Store y Google Play
para **Mezcla**: la política de privacidad y la página de soporte. Nada más.

Sin build ni dependencias: HTML con los estilos dentro. GitHub Pages lo publica
tal cual desde `main`.

| Ruta            | Para qué                                                |
| --------------- | ------------------------------------------------------- |
| `index.html`    | Portada, bilingüe                                       |
| `privacy.html`  | Política de privacidad → `privacyPolicyUrl`             |
| `support.html`  | Soporte → Support URL de App Store Connect              |

## De dónde sale

`privacy.html` y `support.html` **son copias**. El original vive en el repo de la
app, en `mezcla/web/`, que es donde hay que editarlas. Al cambiarlas allí, hay que
copiarlas aquí y hacer push.

Se hizo así porque el código de la app no es público y GitHub Pages solo sirve
desde la raíz o desde `/docs` de un repositorio.

## Por qué existe este repo

`store.config.js` de la app apuntaba antes a `naeku.io/mezcla/privacy` y
`/mezcla/support`. Las dos devolvían **403**, y Apple abre la URL de privacidad
durante la revisión: si no carga, rechaza el envío. Además se le está quitando la
marca naeku a la app, así que alojar ahí su política era incoherente.

## Cuidado con esto

Cada afirmación de la política está verificada contra el código de la app: sin
cuentas, sin analítica, sin publicidad, sin rastreo, sin peticiones de red, y el
micrófono no se pide ni se usa.

**Si la app cambia en cualquiera de esos puntos, la política deja de ser cierta** y
hay que corregirla antes de publicar la versión que introduzca el cambio.
