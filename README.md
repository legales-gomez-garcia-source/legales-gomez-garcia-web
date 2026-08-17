# Sitio web — Legales Gómez García

Landing page de la firma. Es un sitio estático de un solo archivo, sin dependencias
ni proceso de compilación: se despliega tal cual.

## Archivos

| Archivo      | Para qué sirve                                        |
|--------------|-------------------------------------------------------|
| `index.html` | El sitio completo. HTML, CSS y JavaScript en un archivo. |
| `logo.png`   | Logo de la firma. Se usa como favicon.                |

## Configuración

Los datos de contacto y la agenda se editan en el bloque `CONFIG`, dentro de la
etiqueta `<script>` al final de `index.html`:

```js
const CONFIG = {
  whatsapp: "57XXXXXXXXXX",   // 57 + celular, sin "+" ni espacios
  horarios: ["08:00","09:00","10:00","11:00","14:00","15:00","16:00"],
  diasHabiles: [1,2,3,4,5],   // 1 = lunes ... 5 = viernes
  anticipacionDias: 1         // dias habiles minimos de anticipacion
};
```

La dirección de la oficina se edita en el pie de página, en el elemento
`<span id="footDir">`.

## Agenda de reuniones

El calendario bloquea automáticamente sábados, domingos y festivos colombianos.
Los festivos no están escritos a mano: se calculan a partir de la Pascua y de la
Ley 51 de 1983 (Ley Emiliani), que traslada varios festivos al lunes siguiente.
Por eso el calendario sigue siendo correcto en años futuros sin mantenimiento.

Al confirmar, el formulario arma un mensaje con los datos de la reunión y lo abre
en WhatsApp. No hay servidor ni base de datos.

## Despliegue

Cualquier hosting estático sirve. El sitio se publica desde la raíz del repositorio;
no requiere framework ni comando de compilación.
