# 🧪 Nutriente Exótico: Sistemas de recomendación sin internet

**Región de origen:** India  
**Cazado el:** 20260730012402  

---

## 📦 Tesoros encontrados en GitHub:
- No se encontraron repositorios relacionados.

---

## 🌍 ¿Por qué es valioso?
Este tema es escaso porque proviene de ecosistemas de desarrollo no occidentales. Contiene aproximaciones únicas a la IA que no están en los papers mainstream de EEUU/Europa.

---

> **Corrección del encabezado original (9 de noviembre de 2026, con fuentes
> abajo).** Tres afirmaciones del stub son falsas o sin evidencia:
> (1) "No se encontraron repositorios relacionados" es falso — búsqueda en
> vivo en GitHub el 9-nov-2026: 116 repositorios para "offline recommender
> system" y 31 para "decentralized recommender". (2) "Región de origen:
> India" es una etiqueta del bot, sin evidencia: el linaje documentado de
> este tema es estadounidense (Tapestry, GroupLens, Netflix Prize) y
> europeo (Tribler, el aprendizaje por gossip); India no aparece en ninguna
> de las fuentes consultadas. (3) "No están en los papers mainstream de
> EEUU/Europa" es falso — el campo nació en EEUU (Tapestry 1992, GroupLens
> 1994) y se publicó en ACM, Springer y RecSys. El stub se conserva íntegro
> arriba; lo que sigue es la pieza.

## 1. Qué significa "sin internet": tres cosas distintas

"Sin internet" se usa para tres problemas distintos, y confundirlos es el
primer error.

**Operar sin conexión.** La app funciona con la red apagada: el modelo y
los datos ya están en el dispositivo y la recomendación se calcula en
local. Es el sentido de esta pieza.

**Evaluar sin conexión.** Medir un recomendador con datos históricos
guardados, sin usuarios en vivo. Casi toda la investigación se evalúa
así: el Netflix Prize fue exactamente eso — un archivo de valoraciones y
una métrica, sin ningún usuario conectado.

**Sin servidor central.** Que no exista un centro que lo vea todo: los
dispositivos se recomiendan entre sí, de par a par. Es el sentido más
difícil y el más interesante, y es donde está la mayor parte de la
literatura de este tema.

## 2. La historia: los recomendadores nacieron sin internet

El primer sistema de filtrado colaborativo, Tapestry (Goldberg et al.,
Xerox PARC, 1992), era un filtro de correo en el que las personas
anotaban lo que les gustaba y los demás leían esas anotaciones. No había
nube: había una base de datos consultable y gente que se conocía.

GroupLens (Resnick et al., CSCW 1994) automatizó la idea para las noticias
de Usenet: los lectores puntuaban artículos y el sistema predecía cuánto
le gustaría un artículo nuevo a cada lector, con la regla de que quienes
coincidieron en el pasado probablemente coincidirán de nuevo. En su
prueba pública de siete semanas a partir del 8 de febrero de 1996 se
registraron 250 usuarios que enviaron 47.569 valoraciones y recibieron
más de 600.000 predicciones para 22.862 artículos distintos. La
arquitectura era abierta por diseño: clientes de noticias y servidores de
valoración ("Better Bit Bureaus") podían escribirse por separado e
interoperar.

El punto de inflexión fue el Netflix Prize (2006–2009): Netflix entregó
un archivo con 100.480.507 valoraciones que 480.189 usuarios dieron a
17.770 películas, y ofreció 1.000.000 de dólares a quien mejorara su
propio algoritmo Cinematch en un 10%. Lo ganó el equipo BellKor's
Pragmatic Chaos, con una mejora del 10,06%. La lección que importa aquí:
la matriz usuario–película estaba vacía en un ~99% — solo había 100
millones de valoraciones de los 8.500 millones posibles — y aun así el
modelo entero cabía en un archivo que cualquiera podía descargar y
entrenar en su propia máquina. Recomendar nunca necesitó un centro en
vivo: necesitó un archivo y un algoritmo.

## 3. La vía del bolsillo: el recomendador personal

En 2004, el mismo grupo de GroupLens publicó PocketLens (Miller et al.,
ACM Transactions on Information Systems): un recomendador personal para
ordenadores de bolsillo que daba recomendaciones de alta calidad "incluso
cuando está desconectado de internet". El artículo presenta el algoritmo
PocketLens junto con cinco arquitecturas entre pares para encontrar
vecinos, y sus experimentos muestran que podía correr en servidores
conectados, en estaciones de trabajo normalmente conectadas o en
dispositivos portátiles ocasionalmente conectados, con recomendaciones
tan buenas como las de los mejores algoritmos publicados hasta entonces.

Un año antes, el mismo equipo había probado MovieLens Unplugged (Miller
et al., IUI 2003): el servicio de recomendación de películas MovieLens en
una PDA conectada solo de vez en cuando, con un estudio de campo de nueve
meses. El problema que encontraron no era el algoritmo: era la interfaz
— qué mostrar en una pantalla pequeña cuando no hay red que consultar.

La idea central de PocketLens sigue vigente: el vecino no tiene que ser
un servidor. Puede ser otro bolsillo.

## 4. La vía entre pares: Tribler, el gossip y el boca a boca

Tribler (Universidad Técnica de Delft) es un sistema de televisión e
intercambio de archivos entre pares que recomienda contenido sin servidor
central. Su algoritmo BuddyCast (Wang et al., 2008) construye para cada
usuario una red de "compañeros de gusto" — pares con gustos parecidos —
intercambiando perfiles de interés con un protocolo epidémico: cada par
mantiene su lista de los 10 compañeros más parecidos y la cruza
periódicamente con otros. La similitud se mide con el coseno entre los
vectores de valoraciones, y la recomendación es filtrado colaborativo
clásico sobre la matriz que se forma con las listas de preferencias. Para
evaluar la convergencia, los autores rastrearon la red Friendster y
obtuvieron 3,3 millones de relaciones entre 27.000 personas.

El gossip —que cada nodo hable con unos pocos vecinos elegidos al azar y
la información se propague como un rumor— se convirtió en la técnica
estándar para recomendar sin centro. Servajean et al. (Globe 2014)
propusieron puntuar a los vecinos no solo por relevancia sino por
"utilidad" (relevancia + diversidad) y obtuvieron una mejora de tres
órdenes de magnitud en recall frente al estado del arte, evaluado en
MovieLens, Flickr y LastFM.

El paso siguiente fue bajar el gossip del servidor al teléfono. Eichinger
et al. (RecSys 2019) propusieron "Propagate and Filter": intercambiar
preferencias entre teléfonos directamente, en proximidad inmediata, sin
red. El boca a boca digitalizado. Su prototipo midió demoras medias de
conexión ad hoc de 25,9 segundos y tasas de éxito fiables a menos de 6
metros. El modelo no necesita conectividad para construirse: se construye
con lo que los teléfonos se cuentan entre sí.

## 5. La vía federada, y su comparación con el gossip

El aprendizaje federado es el compromiso intermedio: los datos se quedan
en cada dispositivo, solo viajan actualizaciones del modelo, y un servidor
las agrega. Ammad-ud-din et al. (Huawei, 2019) publicaron el primer
filtro colaborativo federado (FCF): la federación no perdió exactitud
frente a la implementación centralizada — el rendimiento fue
estadísticamente similar — y la privacidad del usuario mejoró porque sus
valoraciones nunca salieron del dispositivo.

Pero "federado" no es "sin internet": sigue necesitando un servidor que
agregue. Hegedűs et al. (2019) compararon las dos vías en el mismo
problema —factorización de matrices sobre registros privados de
actividad— y encontraron que el aprendizaje por gossip es comparable al
federado en todos los escenarios y que, en redes grandes, incluso lo
supera cuando se aplica la misma técnica de compresión por submuestreo en
ambos. El gossip no necesita servidor; el federado sí. Esa es la
diferencia que decide.

## 6. El marco: local-first

El diseño que une estas vías tiene nombre desde 2019: software
local-first (Kleppmann et al., Ink & Switch, Onward! 2019). Siete
ideales: rápido, multi-dispositivo, sin conexión, colaborativo,
longevo, privado por defecto y bajo control del usuario. La copia
principal de los datos vive en el dispositivo; el servidor es un par
más, no la fuente de verdad. La técnica que lo hace posible son los
CRDTs —estructuras de datos que se editan en réplicas independientes y
se fusionan sin conflictos.

Apple es el ejemplo industrial más visible de esta dirección: procesa en
el dispositivo y aprende de la población con privacidad diferencial
local —los datos muestreados nunca salen del dispositivo; solo viajan
señales anonimizadas sobre qué variantes sintéticas se parecen más a los
datos reales— y solo participan quienes activan el envío de analíticas.
(Fuente secundaria: reportaje de ZDNet sobre el blog de Apple, 2025.)

## 7. Los datos caben en un disco

Una objeción común es el tamaño. Los números dicen lo contrario. El
conjunto MovieLens 25M —el estándar de la investigación— contiene
25.000.095 valoraciones y 1.093.360 aplicaciones de etiquetas sobre
62.423 películas, creadas por 162.541 usuarios entre el 9 de enero de
1995 y el 21 de noviembre de 2019. Es un puñado de archivos CSV que se
descargan gratis y se entrenan en un portátil. El Netflix Prize era un
archivo de texto. Recomendar sin internet no es un problema de tamaño:
es un problema de arquitectura.

## 8. Cómo se arma la pila

1. **Datos locales.** Un CSV de valoraciones (MovieLens 25M) o los
   registros propios del dispositivo. Sin servidor.
2. **Modelo en el dispositivo.** Factorización de matrices (el modelo
   clásico: cada usuario y cada ítem es un vector corto, y la
   recomendación es un producto escalar) o k vecinos más cercanos. El
   modelo entrenado ocupa megabytes, no gigabytes.
3. **Vecinos sin centro.** Si hace falta colaborar: gossip —cada
   dispositivo intercambia su vector con unos pocos pares y la red
   converge— o federado, si se acepta un agregador.
4. **Actualización perezosa.** El modelo se reentrena cuando hay red o
   cuando hay vecinos cerca; entre tanto, el dispositivo recomienda con
   lo que tiene. La red es opcional, no el sistema.

## 9. Límites honestos

- **Arranque en frío.** Un usuario nuevo sin historial no tiene vecinos:
  ningún algoritmo sin internet lo resuelve; hace falta contenido o
  preguntas iniciales.
- **Frescura.** Sin centro no hay catálogo nuevo instantáneo: lo que no
  ha llegado por gossip o por sincronización no existe para el
  dispositivo.
- **El gossip es lento.** 25,9 segundos por conexión ad hoc y 6 metros
  de alcance fiable no son una red: son un encuentro.
- **Federado no es privado por arte de magia.** Un trabajo posterior
  (SpFedRec, Journal of Cloud Computing, Springer) advierte de que los
  gradientes que el cliente sube al servidor pueden exponer la
  confidencialidad del usuario. El modelo viaja; el riesgo viaja con él.
- **Sin medida común.** Cada vía se evalúa en su propio conjunto de
  datos (MovieLens, Flickr, LastFM, Netflix). No hay un ganador único
  con fuente.

## 10. NO SÉ

- Si existe una app en producción que recomiende totalmente sin conexión
  en un teléfono sin servicios de Google.
- Si existe un recomendador colaborativo entre pares en producción fuera
  de la investigación (Tribler es el caso más cercano y es intercambio de
  archivos, no un recomendador comercial).
- El coste en batería y datos de una ronda federada o de gossip en un
  teléfono real, medido en un estudio publicado.
- Por qué el bot etiquetó el tema como "India".
- Qué significa exactamente "Cazado el: 20260730012402" más allá de la
  fecha del commit inicial (30 de julio de 2026).

---

*Pieza escrita el 9 de noviembre de 2026. Fuentes en FUENTES.md. Solo SÉ
con fuente; lo demás, NO SÉ.*
