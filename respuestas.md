
# Visualizacion de datos: Datadog, La Estrella del Norte :star:
## Mantiene la vista en el horizonte
![North Star](http://cdn.lowgif.com/full/4c0f211082b1edb6-.gif)

Construir un negocio exitoso no se trata de subir escaleras o defenderse de la competencia en un espacio en particular; se trata de generar impulso y seguir avanzando.
Cuando un negocio crece, los "dolores de crecimiento" son más que simples obstáculos u obstrucciones, a veces no se mueve tanto como le gustaría.
Has perdido de vista ese horizonte, y eso es realmente de lo que estoy aquí para hablar hoy.

La forma de Datadog de mantener lo visual abierto a través de la visualización de métricas, trazas y registros en una plataforma integrada es la forma más efectiva de ver siempre el horizonte; recolectando datos
a partir de cientos de tecnologías para visualización, resolución de problemas, aprendizaje automático, alertas y más, mantenga el visual abierto. No pierdas tu camino.
Nunca pierda de vista la dirección en la que quiere ir. No se pierda en un mar de resolución de problemas, mire hacia la estrella del norte para ver la dirección.

Repasemos más a fondo cómo funciona Data-dog, qué tan simple y rápido es comenzar:

## Configuracion Rapida
### Sistema Operativo
Ya sea que sea un maestro de los sistemas operativos de Microsoft, un Linux Ninja o un asistente de Mac OS; o ha empaquetado su aplicación (mírelo, en serio) Datadog lo tiene cubierto;
Regístrese para obtener una cuenta gratuita de Datadog, haga clic en Integrations > Agent, descargue su agente y prepárese para ingerir.

### Tags
Como parte de nuestra configuración, queremos usar tags en nuestro archivo de configuración del agente. Piense en las tags como una forma de agregar dimensiones a las telemetrías de Datadog para que se puedan filtrar, agregar y
comparar visualizaciones en Datadog. Inicie su agente una vez que haya agregado sus tags al archivo de configuración del agente y vea el nuevo host en la consola de Datadog.

### Bases de datos
Pero, ¿y si quiero monitorear bases de datos?
Datadog tiene más de 400 [integraciones compatibles](https://docs.datadoghq.com/integrations/)
Asegúrese de editar el archivo de configuración correcto (conf.yaml) como lo he hecho a continuación, en mi caso particular, me gustaría monitorear una base de datos postgreSQL en mi escritorio de desarrollo de Windows.

## Chequeos personalizados
¿Hay chequeos de agente personalizados? Esas no son integraciones realmente compatibles ...
De hecho, lo son. Siempre que la verificación esté escrita en un lenguaje compatible (piense en Go, NodeJS, Python, etc.). He escrito un breve script que genera aleatoriamente un número, entre 0 y 9999.
Para crear una verificación de agente personalizada, necesitará 2 archivos:

    1. Archivo de configuracion
    2. Archivo de comandos

![Pro Tip](https://u.cdn.sera.to/content/images/93/23193/23193.png) ¿Sabías?
¿Sabías que podemos cambiar el intervalo de recopilación sin modificar los archivos de verificación de secuencia de comandos que creó?


## Visualización de datos y API de Datadog

Hablemos de la [API de Datadog] (https://docs.datadoghq.com/api/) y los horarios con métricas; como puede ver a continuación, creé el panel de control "Hello Datadog Dashboard" usando Postman.
[Postman] (https://www.postman.com/) es una herramienta de desarrollo de software que nos permite probar llamadas a API, en este caso particular lo configuré para usar mi cuenta y envié las siguientes cargas útiles:
### Carga 1:
### Carga 2:
### Carga 3:

Ahora que hemos creado nuestro panel desde Postman a través de llamadas a la API, veamos cómo se ve:

Podemos ver el promedio de CMetric, nuestro resumen y cualquier anomalía asociada, realmente genial.

![Pro Tip](https://u.cdn.sera.to/content/images/93/23193/23193.png) ¿Sabías?
Las anomolias le brindan una tendencia histórica para las métricas, cuando una métrica está fuera del umbral, la línea se vuelve roja.
Esto muestra que la métrica se está comportando fuera del rango histórico "normal"; ¿Puedes pensar en algún caso de uso?

## Seguimiento de datos

