Derick, te dejo lo de las políticas nuevas (HAA-LEG-002): https://github.com/derick061020/hispaniola/pull/7

Ya lo mergeaste, gracias. Trae las páginas de cancelación, términos y privacidad con el texto del PDF, las edades nuevas (0-3 / 4-12) y el depósito también con efectivo. Después del merge subí a la misma rama las casillas de aceptación del checkout (commit bf32cdb, aplica limpio sobre backend-odoo): hay que traerlo también.

Lo que te toca en Odoo, por prioridad:
1. Que ninguna reserva se confirme sin depósito cobrado, también con efectivo: /pay siempre por el depósito y /confirm o el webhook nunca confirman sin él.
2. Edades: infants = menores de 4 y children = 4-12 en precios, correos y parte de embarque.
3. Cancelar con 7 días o más devuelve todo lo pagado, no solo el depósito. Con menos de 7, nada.
4. Traer bf32cdb y guardar en la reserva el campo nuevo legal_acceptance que llega en el sync (fecha y hora, versión, canal, autoriza imagen sí/no), visible en la ficha. Detalle en PARA-DERICK.md §4.
5. Poner el enlace a /legal/cancellation-policy en el correo de confirmación.

Todo explicado en docs/proceso/politicas-haa-leg-002/PARA-DERICK.md. Avísame cuando esté en producción.
