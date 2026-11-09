# Fuentes — Sistemas de recomendación sin internet

Consultadas el 9 de noviembre de 2026. Cada fuente dice qué afirma.
Primarias salvo que se marque lo contrario.

1. **Goldberg et al. 1992 — Tapestry.** "Using collaborative filtering to
   weave an information tapestry", Communications of the ACM 35(12),
   pp. 61–70. Afirma: el primer sistema de filtrado colaborativo; las
   personas anotaban lo que les gustaba y los demás leían esas anotaciones.
   Citado aquí vía la historia del campo (fuente 2) y el prólogo de
   *Recommender Systems* (Cambridge). No se leyó el texto completo del
   artículo original en esta sesión.
   - https://ar5iv.labs.arxiv.org:443/html/2209.01860
   - https://www.cambridge.org/core/books/abs/recommender-systems/foreword/1BF6B3AA96EEBCB44502B62E63DD0C6F

2. **Resnick et al. 1994 — GroupLens.** "GroupLens: an open architecture
   for collaborative filtering of netnews", Proceedings of ACM CSCW 1994,
   pp. 175–186. Afirma: primer filtrado colaborativo automatizado; la
   regla de que quienes coincidieron en el pasado probablemente
   coincidirán de nuevo; arquitectura abierta con clientes de noticias y
   servidores de valoración ("Better Bit Bureaus") interoperables.
   - http://sistemas-humano-computacionais.wdfiles.com/local--files/capitulo%3Aredes-sociais/GroupLens.pdf

3. **Konstan et al. 1997 — GroupLens en Usenet.** "GroupLens: Applying
   collaborative filtering to Usenet news", Communications of the ACM
   40(3). Afirma: prueba pública de siete semanas desde el 8 de febrero
   de 1996 — 250 usuarios, 47.569 valoraciones, más de 600.000
   predicciones para 22.862 artículos distintos.
   - https://www.researchgate.net/publication/2314792_GroupLens_Applying_collaborative_filtering_to_Usenet_news

4. **Miller et al. 2004 — PocketLens.** "PocketLens: Toward a personal
   recommender system", ACM Transactions on Information Systems. Afirma:
   recomendaciones de alta calidad en ordenadores de bolsillo "incluso
   cuando está desconectado de internet"; algoritmo PocketLens más cinco
   arquitecturas entre pares para encontrar vecinos; tan buenas como los
   mejores algoritmos publicados hasta entonces.
   - https://dl.acm.org/doi/10.1145/1010614.1010618

5. **Miller et al. 2003 — MovieLens Unplugged.** "MovieLens Unplugged:
   Experiences with an Occasionally Connected Recommender System",
   IUI 2003, GroupLens Research. Afirma: el servicio MovieLens en una
   PDA conectada solo de vez en cuando; estudio de campo de nueve meses;
   el problema central era la interfaz, no el algoritmo.
   - http://files.grouplens.org/papers/miller-iui03.pdf

6. **Wang et al. 2008 — Tribler / BuddyCast.** "Personalization on a
   peer-to-peer television system", Multimedia Tools and Applications
   36:89–113, DOI 10.1007/s11042-006-0075-6. Afirma: BuddyCast construye
   redes de "compañeros de gusto" con protocolo epidémico; similitud por
   coseno entre vectores de valoraciones; recomendación por filtrado
   colaborativo sobre la matriz de preferencias; convergencia evaluada
   con un rastreo de Friendster (3,3 millones de relaciones entre
   27.000 personas).
   - https://repository.tudelft.nl/file/File_3904987c-5e65-4d81-81d3-02107f14baa3

7. **Servajean et al. 2014 — Gossip con diversidad.** "Exploiting
   Diversification in Gossip-Based Recommendation", Globe 2014, HAL
   lirmm-01088730. Afirma: puntuar vecinos por "utilidad" (relevancia +
   diversidad) da una mejora de tres órdenes de magnitud en recall
   frente al estado del arte, evaluado en MovieLens, Flickr y LastFM.
   - https://hal-lirmm.ccsd.cnrs.fr/lirmm-01088730/document

8. **Eichinger et al. 2019 — Propagate and Filter.** "On Gossip-based
   Information Dissemination in Pervasive Recommender Systems", RecSys
   2019, arXiv:1908.05544. Afirma: intercambio de preferencias entre
   teléfonos en proximidad inmediata, sin red; el modelo no necesita
   conectividad para construirse; prototipo con demoras medias de
   conexión ad hoc de 25,9 segundos y éxito fiable a menos de 6 metros.
   - https://arxiv.org/pdf/1908.05544

9. **Ammad-ud-din et al. 2019 — FCF.** "Federated Collaborative
   Filtering for Privacy-Preserving Personalized Recommendation System",
   arXiv:1901.09888. Afirma: primer filtro colaborativo federado; el
   rendimiento es estadísticamente similar al centralizado, sin pérdida
   de exactitud; las valoraciones nunca salen del dispositivo.
   - https://arxiv.org/pdf/1901.09888

10. **Hegedűs et al. 2019 — Gossip contra federado.** "Decentralized
    Recommendation based on Matrix Factorization: A Comparison of Gossip
    and Federated Learning", DMLE 2019, Springer CCIS 1167. Afirma: el
    aprendizaje por gossip es comparable al federado en todos los
    escenarios y en redes grandes incluso lo supera con la misma
    compresión por submuestreo; el gossip no necesita servidor de
    agregación.
    - http://publicatio.bibl.u-szeged.hu/18455/1/all.pdf

11. **Netflix Prize (2006–2009).** Afirma: 100.480.507 valoraciones de
    480.189 usuarios a 17.770 películas, escala 1–5; premio de
    1.000.000 de dólares; ganado por BellKor's Pragmatic Chaos con una
    mejora del 10,06% sobre Cinematch; la matriz estaba vacía en un
    ~99%. Consultada la entrada de Wikipedia y el análisis de Rasch.
    - https://en.wikipedia.org/wiki/Netflix_Prize
    - https://www.rasch.org/rmt/rmt233d.htm

12. **MovieLens 25M — GroupLens.** README oficial del conjunto de datos.
    Afirma: 25.000.095 valoraciones y 1.093.360 aplicaciones de etiquetas
    sobre 62.423 películas, creadas por 162.541 usuarios entre el 9 de
    enero de 1995 y el 21 de noviembre de 2019; descarga gratuita.
    - https://files.grouplens.org/datasets/movielens/ml-25m-README.html

13. **Kleppmann et al. 2019 — Local-first software.** "Local-first
    software: You own your data, in spite of the cloud", Onward! 2019,
    ACM, DOI 10.1145/3359591.3359737. Afirma: siete ideales (rápido,
    multi-dispositivo, sin conexión, colaborativo, longevo, privado por
    defecto, bajo control del usuario); la copia principal vive en el
    dispositivo; los CRDTs como fundamento técnico. Consultada la entrada
    de Wikipedia, que recoge los siete ideales y el DOI.
    - https://en.wikipedia.org/wiki/Local-first_software

14. **Apple — privacidad diferencial en el dispositivo (SECUNDARIA).**
    Reportaje de ZDNet sobre el blog de Apple (2025). Afirma: Apple
    aprende de la población con privacidad diferencial local; los datos
    muestreados nunca salen del dispositivo; solo participan quienes
    activan el envío de analíticas; ya se usa en Genmoji. No se leyó el
    blog original de Apple en esta sesión: la fuente es el reportaje.
    - https://www.ZDNET.com/article/how-apple-plans-to-train-its-ai-on-your-data-without-sacrificing-your-privacy/

15. **SpFedRec (SECUNDARIA).** "A split-federated learning and
    edge-cloud based efficient and privacy-preserving large-scale item
    recommendation model", Journal of Cloud Computing, Springer.
    Afirma: los gradientes que el cliente sube al servidor pueden
    exponer la confidencialidad del usuario. Citado como advertencia de
    un trabajo posterior, no como medición verificada aquí.
    - https://link.springer.com/article/10.1186/s13677-023-00435-5

16. **Búsqueda en vivo en GitHub, 9 de noviembre de 2026.** Afirma:
    116 repositorios para "offline recommender system" y 31 para
    "decentralized recommender". Búsqueda por API de GitHub, realizada
    en esta sesión para corregir el stub. Sin URL: es una consulta en
    vivo, no una página.

## Visto y no usado

- La historia breve de los recomendadores (arXiv:2209.01860) para el
  contexto de Tapestry y GroupLens; las cifras concretas se tomaron de
  las fuentes primarias 2 y 3, no de este resumen.
- La entrada de Wikipedia de GroupLens Research para la fecha de
  fundación del laboratorio (1992) y el premio CSCW 2019 al artículo de
  1994; no se usó ninguna cifra de esa página en la pieza.
