# Presupuesto con permuta de alojamiento: viabilidad, riesgos e implantación

## 1. ¿Es viable?

Sí, y es un modelo habitual (permuta / *barter*) en hoteles pequeños e independientes: tienen habitaciones vacías con coste marginal bajo y poco flujo de caja para pagar servicios digitales. A ti te reduce gasto fijo mientras viajas. Funciona bien cuando:

| Condición | Por qué |
|---|---|
| Hotel independiente o hostal con decisor único (dueño/a) | Un grupo hotelero tiene procesos, contratos y revenue managers que complican la permuta. |
| Temporada baja o ocupación floja | El hotel «regala» noches que no vendería. En temporada alta tu habitación tiene coste de oportunidad y se renegocia. |
| Estancias ≥ 4 semanas | Se aplica tarifa mensual y compensa el trabajo administrativo. |
| Alcance cerrado y entregables claros | Si el proyecto crece, crece la deuda de noches. |

No es buena idea cuando el proyecto es largo y de alcance abierto (mantenimiento continuo, e-commerce complejo), cuando el hotel está en venta o en crisis financiera, o cuando necesitas efectivo para costes que no se pagan en noches (impuestos, licencias, hosting).

## 2. Cómo se calcula la reducción

```
Valor del paquete = alojamiento (tarifa mensual × noches/30) + servicios incluidos
Crédito aplicado  = valor del paquete × (1 − margen de seguridad)   [tope: presupuesto]
Efectivo a cobrar = presupuesto − crédito aplicado
```

Decisiones de diseño que importan:

1. **Qué tarifa usar.** Tres opciones en la herramienta: mensual (recomendada, es lo que realmente cobraría el hotel), diaria (*rack rate*, infla el descuento y el hotel lo discutirá) y **tu coste alternativo** (lo que pagarías tú en otro sitio). Si usas la diaria y el cliente acepta, tú pierdes: el hotel valora la noche a su coste, no a su precio de lista.
2. **Servicios incluidos suman; los no incluidos son riesgo.** Desayuno, comida, cena, lavandería, toallas, limpieza, luz/AC, parking, tasa turística. Cada servicio tiene un estado: *incluido*, *no incluido* o *sin confirmar*. Lo «sin confirmar» se trata como exposición y dispara una alerta roja.
3. **Margen de seguridad (15 % por defecto).** Reserva para extras no previstos, subidas de tarifa y retrasos.
4. **Tope en el presupuesto.** Si el alojamiento vale más que el trabajo, el excedente se muestra y se avisa; no se «regala» a nadie.
5. **Efectivo mínimo.** Alerta si cobras menos del 25 % en dinero: tus costes fijos de negocio no se pagan con noches.

## 3. Problemas por no haberlo hablado antes

| Problema | Consecuencia típica | Qué acordar |
|---|---|---|
| Servicios no definidos (desayuno, lavandería, toallas…) | Pagas extras que «ya estaban» en tu cabeza y el presupuesto deja de salir a cuenta. | Lista cerrada de incluidos/no incluidos, por escrito. |
| Tarifa sin impuestos | Coste +10–21 % no previsto. | Confirmar si incluye IVA y tasa turística. |
| Subida de tarifa en temporada alta o evento | El hotel te pide cambiar de habitación, pagar diferencia o irte. | Tarifa congelada y habitación asignada para todo el periodo. |
| Overbooking o venta del hotel | Te quedas sin alojamiento a mitad de proyecto. | Cláusula de compensación en efectivo o noches equivalentes. |
| Desfase entre trabajo y estancia | Terminas el trabajo y te quedan noches (o al revés: te quedan horas y no hay noches). | Calendario: noches ↔ hitos de entrega. La herramienta compara días de trabajo necesarios con noches. |
| Retrasos del cliente (contenido, aprobaciones) | Las noches se consumen y el proyecto no avanza. | Plazos de feedback y penalización por demora (pausa del reloj de la estancia). |
| Alcance que crece | Deuda de trabajo no compensada. | Cambios presupuestados aparte (efectivo o noches adicionales). |
| Cancelación por cualquiera de las partes | Disputa sobre qué se debe. | Prorrata: noches usadas vs. trabajo entregado. |
| Fiscalidad | La permuta suele ser operación sujeta a impuestos: ambas partes facturan y pueden deber IVA e impuesto sobre beneficios sobre un servicio que no cobraste en dinero. | Factura cruzada y gestor. Importante en España/UE, y distinto en Latinoamérica. Valida con tu asesor. |
| Fianza | Dinero inmovilizado, riesgo de no devolución. | Devolución o descuento de la fianza en el acuerdo. |
| Condiciones del alojamiento para trabajar | WiFi malo, ruido, sin escritorio: pierdes productividad y el cliente espera igual. | Prueba de velocidad previa, espacio de trabajo, horarios. |
| Costes de terceros (dominio, hosting, licencias, impresión) | Los asumes tú sin querer. | Cláusula: a cargo del cliente. |
| Propiedad intelectual | El cliente usa el logotipo sin haber completado la compensación. | Cesión al completar el pago/permuta. |
| Mantenimiento posterior | Soporte gratuito indefinido. | Alcance y cuota separados. |
| Relación personal | Mezclar convivencia y trabajo: el cliente te ve «siempre disponible». | Horarios de trabajo y canal único de comunicación. |

## 4. Proceso de negociación recomendado

1. **Antes de proponerlo**: define tu precio normal en efectivo y tu coste alternativo por noche. Sin eso no sabes si el trato te conviene.
2. **Primera reunión**: presenta el presupuesto en euros y plantea la permuta como una *opción*, no como la condición. «Esto cuesta X. Si prefieres, podemos compensar parte con alojamiento.»
3. **Recoge los datos** en la herramienta (tarifa diaria, mensual, impuestos, servicios incluidos, fianza, fechas).
4. **Revisa las alertas** y cierra todo lo rojo antes de aceptar.
5. **Envía el texto generado** (sección 6) por email y pide confirmación escrita.
6. **Contrato breve** de 1–2 páginas con las condiciones de la sección 5 de la herramienta.
7. **Seguimiento**: revisa mensualmente noches usadas vs. hitos entregados.

## 5. Implantación

La herramienta es un único archivo, `presupuesto-permuta/index.html`, sin dependencias ni servidor. Ábrelo en el navegador o publícalo con tu portafolio.

- **Datos**: se guardan en el navegador (`localStorage`). Se pueden exportar e importar como JSON para guardar un acuerdo por cliente.
- **Salida**: texto copiable para email y vista imprimible / PDF.
- **Hojas de ruta posibles** (no incluidas aún): varias estancias por cliente, calendario de hitos, plantilla de contrato, multiusuario con base de datos, ajuste automático del crédito si cambian las noches.

## 6. Pendientes que dependen de ti

- Valores por defecto de servicios (desayuno 8 €, comida 15 €, etc.) y tu margen: ajústalos a tus destinos.
- Fiscalidad aplicable según tu país y el del hotel.
- Si quieres la plantilla de contrato, dime en qué jurisdicción trabajas y la redacto.
