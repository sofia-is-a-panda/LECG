# LECG : Learning ECG
<p align="justify">
¡Bienvenidos! Somos un grupo de estudiantes de 7mo ciclo de la carrera de Ingeniería Biomédica de la PUCP y UPCH. Queremos compartir nuestro proyecto de Introducción a Señales Biomédicas con usted, en este repositorio podrá encontrar toda la información sobre nuestro dispositivo.
</p>

***

# **Tabla de contenidos**
1. [Introducción](#id1)
2. [Contexto](#id2)
3. [Problemática](#id3)
4. [Estado de arte](#id4)
5. [Propuesta de solución](#id5)
6. [Características técnicas](#id6)
7. [Entrevistas a stakeholders](#id7)
8. [Integrantes](#id8)
9. [Docentes del curso](#id9)
10. [Referencias bibliográficas](#id10)
   
***
# Resumen

<p align="justify">
LECG (Learn ECG) aborda el desafío de mejorar las habilidades de interpretación de electrocardiogramas (ECG) en entornos con recursos limitados, como Pasco, Perú. Aprovechando la tecnología accesible y las técnicas avanzadas de aprendizaje automático, LECG permite a estudiantes y profesionales médicos practicar y perfeccionar sus capacidades diagnósticas de manera efectiva. La interfaz intuitiva basada en Python apoya la interacción del usuario, proporcionando retroalimentación detallada y elementos de gamificación para fomentar el aprendizaje activo. Validado con alta sensibilidad y especificidad en la detección de fibrilación auricular utilizando un clasificador SVM con núcleo RBF, el proyecto demuestra avances significativos en la aplicación de tecnología para la educación médica y la mejora del cuidado cardiovascular.
</p>

# Motivación

<p align="justify">
En el Perú, las enfermedades cardiovasculares representan una de las principales causas de muerte, lo que resalta la necesidad urgente de mejorar la formación y habilidades de diagnóstico en cardiología. Las disparidades en el acceso a especialistas y tecnología médica entre las áreas urbanas y rurales, como Pasco, agravan esta situación. La pandemia ha exacerbado estos desafíos, limitando las oportunidades de aprendizaje práctico y efectivo en la interpretación de electrocardiogramas (ECG) para los estudiantes de medicina.

Frente a este contexto, surge la necesidad de desarrollar soluciones innovadoras que aborden estas brechas y fortalezcan las capacidades diagnósticas de los futuros profesionales de salud. LECG (Learn ECG) se propone como una herramienta educativa revolucionaria que utiliza tecnología accesible y técnicas avanzadas de aprendizaje automático para proporcionar una plataforma de aprendizaje interactiva y efectiva. Al combinar elementos de gamificación y retroalimentación detallada, LECG no solo mejora la formación académica, sino que también contribuye a la detección temprana y precisa de anomalías cardíacas, como la fibrilación auricular.

Esta iniciativa no solo busca mejorar la educación médica en entornos con recursos limitados, sino también contribuir significativamente a la atención cardiovascular, salvando potencialmente numerosas vidas al capacitar mejor a los profesionales de la salud para enfrentar los desafíos clínicos del futuro.
</p>

# 1. Introducción<a name="id1"></a>

<p align="justify">
En cada latido, el corazón se despolariza para desencadenar su contracción. Esta actividad eléctrica se transmite por todo el cuerpo y puede ser captada en la piel. Este es el principio detrás del electrocardiograma (ECG). Una máquina de ECG registra esta actividad a través de electrodos en la piel y la muestra gráficamente. Un ECG implica la conexión de 10 a 12  cables eléctricos al cuerpo: uno a cada miembro y seis a través del pecho [13].
</p>

<p align="justify">
La electrocardiografía es una parte fundamental de la evaluación cardiovascular, siendo una herramienta esencial para investigar arritmias cardíacas y diagnosticar trastornos como el infarto de miocardio. Se registra la actividad eléctrica del corazón a través de electrodos en las extremidades y el pecho, produciendo un electrocardiograma (ECG) que refleja la despolarización y repolarización del músculo cardíaco [1].
</p>

<p align="justify">
Los seis electrodos torácicos (V1 a V6) y los seis de miembros (I, II, III, aVR, aVL y aVF) ofrecen diferentes vistas del corazón, permitiendo una evaluación detallada de sus superficies. Se utiliza una grabación prolongada de una derivación, generalmente la II, para evaluar el ritmo cardíaco con precisión. A pesar de que el estándar de 12 derivaciones del ECG ha permanecido constante durante décadas, se han explorado métodos para reconstruir derivaciones precordiales a partir de derivaciones existentes, lo que podría mejorar la interpretación del ECG [1].
</p>

<p align="justify">
Una estrategia para reducir el número de derivaciones consiste en excluir ciertas derivaciones del registro del ECG y, en su lugar, reconstruir las excluidas a partir de las existentes, ya sea mediante una reconstrucción general o específica del paciente. Estudios han demostrado que la reconstrucción paciente-específica, utilizando ciertas derivaciones de miembros y al menos una precordial, puede permitir la reconstrucción de hasta cuatro derivaciones precordiales. Esto ofrece una perspectiva prometedora para mejorar la precisión en la interpretación del ECG estándar, especialmente en casos como el infarto de miocardio. Se ha estudiado cómo se puede reconstruir el ECG de 12 derivaciones a partir de diferentes subconjuntos de derivaciones, siempre incluyendo las derivaciones de miembros I y II y al menos una derivación precordial. Se concluyó que la reconstrucción general permite la reconstrucción de una o dos derivaciones precordiales, mientras que la reconstrucción específica del paciente permite reconstruir hasta cuatro derivaciones. La mejor combinación de derivaciones con cuatro derivaciones precordiales eliminadas fue I, II, V2 y V5. Sin embargo, la reconstrucción específica del paciente presupone un ECG previamente registrado y se ve afectada con el tiempo, probablemente por cambios posturales [2].
</p>

# 2.  Contexto<a name="id2"></a>

<p align="justify">
Según cifras del Instituto Nacional Cardiovascular (INCOR) la enfermedad cardiovascular representa la segunda causa de muerte en el Perú, con una incidencia del 20% [1].  Esta condición de salud se posiciona como una preocupación significativa en el país. Sin embargo, a nivel global, la gravedad de esta enfermedad es aún más pronunciada, ya que según la Organización Mundial de la Salud (OMS) constituye la principal causa de fallecimiento, con aproximadamente el 30% de las muertes registradas atribuidas a problemas cardiovasculares [1].
</p>

<p align="justify">
Asimismo, la Sociedad Peruana de Cardiología (SOPECARD) destaca que en nuestro país se reportan diariamente más de 100 casos de infarto agudo al miocardio [2]. Esta condición médica representa una de las emergencias más comunes, con consecuencias significativas para la salud pública. Se estima que aproximadamente una tercera parte de los pacientes que experimentan este tipo de evento fatalmente no logran reconocer los síntomas a tiempo o no pueden acceder a atención médica oportuna. Esto conlleva a un número considerable de fallecimientos tanto en los hogares como en el trayecto hacia centros de atención sanitaria [2].
</p>

<p align="justify">
El monitoreo efectivo de estos pacientes en hospitales y centros de salud requiere la utilización de equipos médicos de alto costo, los cuales solo pueden ser operados por personal médico debidamente capacitado. Sin embargo, en el contexto peruano, la disponibilidad de dicho personal es limitada, con solo 42 médicos especialistas por cada 100,000 habitantes [3]. Esta escasez de personal capacitado representa un desafío significativo para el adecuado seguimiento y atención de los pacientes en todo el país.
</p>

<p align="justify">
Además, otro factor importante a considerar es la ubicación geográfica de los centros de salud, ya que esto influye en la cantidad de personal capacitado disponible en cada localidad. Las áreas remotas y rurales, en particular, pueden enfrentar una mayor dificultad para acceder a profesionales médicos debidamente formados, lo que puede afectar negativamente la calidad de la atención médica y el monitoreo de los pacientes. Esto se refleja claramente en los datos proporcionados por el Colegio Médico del Perú (CMP). Actualmente, el país cuenta con un total de 106,595 médicos colegiados, de los cuales 1,292 tienen una especialización en cardiología. Es importante destacar que de estos médicos especializados, 735 están ubicados en Lima [4]. En contraste, en la región de Pasco solo se cuenta con dos especialistas, lo cual es una cifra muy preocupante [4].
</p>

<p align="justify">
También es importante tener en cuenta que, de acuerdo con el reporte de inspección de carencias emitido por el Ministerio de Salud (MINSA) hasta el año 2023, de los 247 hospitales activos a nivel nacional, 225 carecen de una infraestructura y equipamiento adecuados, lo que implica que no alcanzan los estándares mínimos requeridos. Asimismo, la mayoría de los centros de atención primaria de salud, que suman un total de 8,783, también muestran condiciones deficientes. De esta cifra, 8,315, es decir, el 95%, no cumplen con los requisitos básicos para proporcionar un servicio de calidad a los pacientes [5].
</p>

<p align="justify">
En gran parte esto se debe a que el mercado de equipamiento médico en Perú depende principalmente de importaciones debido a la producción nacional marginal. En 2019, las importaciones superaron los 351 millones de USD, con un total de 1,605 millones de USD en el período 2015-2019 y un crecimiento promedio del 11% durante ese lapso. Sin embargo, el ámbito de la electromedicina, en donde está incluido la exportación de electrocardiógrafos, experimentaron disminuciones en las importaciones en comparación con 2015. La falta de importaciones de electrocardiógrafos en Perú refleja una limitación en la disponibilidad de este equipo médico crucial en el país. La escasez de estos dispositivos tiene varias implicaciones negativas en el sistema de salud como limitaciones en el diagnóstico y monitoreo de las enfermedades cardiacas e incrementar aún más la brecha en el acceso de atención médica en las zonas rurales [6].
</p>

[1] “Enfermedades al corazón son la segunda causa de muerte en el Perú”, Essalud, 12-mar-2022. [En línea]. Disponible en: http://noticias.essalud.gob.pe/?inno-noticia=enfermedades-al-corazon-son-la-segunda-causa-de-muerte-en-el-peru. [Consultado: 03-abr-2024].

[2] K. Ramírez, “El 85% de peruanos que sufre un infarto al miocardio sobrevive al año si tienen un tratamiento oportuno”, Divulga Científica, 17-ene-2024. [En línea]. Disponible en: https://divulga.cientifica.edu.pe/nuestra-ciencia/el-85-de-peruanos-que-sufre-un-infarto-al-miocardio-sobrevive-al-ano-si-tienen-un-tratamiento-oportuno/. [Consultado: 03-abr-2024].

[3]	Ministerio de Salud (MINSA), “Información de recursos humanos en el sector salud”, 2021. Disponible en: https://cdn.www.gob.pe/uploads/document/file/3281380/Informaci%C3%B3n%20de%20Recursos%20Humanos%20en%20el%20sector%20Salud.pdf?v=1655762418. [Consultado: 03-abr-2024].

[4] “MÉDICOS ESPECIALISTAS DEL CMP”, Colegio Médico del Perú - Consejo Nacional, 13-jun-2022. [En línea]. Disponible en: https://www.cmp.org.pe/medicos-especialistas-del-cmp/. [Consultado: 03-abr-2024].

[5] Ministerio de Salud (MINSA), “Diagnóstico de brechas de infraestructura o acceso de servicios del sector salud”, 2024. Disponible en: https://www.minsa.gob.pe/Recursos/OTRANS/08Proyectos/2022/Diagnostico-Infraestructura-Sector-Salud-2024-2026.pdf. [Consultado: 03-abr-2024].

[6] E. Mercado De Equipamiento Y Material Médico En Perú, “EL ESTUDIO DE MERCADO,” 2020. [En línea]. Disponible en: https://www.icex.es/content/dam/es/icex/oficinas/065/documentos/2021/02/documentos-anexos/DOC2021871587.pdf

[7] Ministerio de Salud (MINSA), “Diagnóstico de brechas de infraestructura o acceso de servicios del sector salud”. Disponible en: https://www.minsa.gob.pe/Recursos/OTRANS/08Proyectos/2022/Diagnostico-Infraestructura-Sector-Salud-2024-2026.pdf. [Consultado: 02-jul-2024].



</p>



# 3.  Problemática<a name="id3"></a>

<p align="justify">
La región de Pasco enfrenta una grave falta de acceso a especialistas y a tecnología como los (ECG), lo que, junto con una infraestructura médica inadecuada, complica el tratamiento y diagnóstico de enfermedades cardíacas y obstaculiza el acceso a una atención cardiovascular de calidad [7]. Además, los futuros profesionales de la salud demandan una plataforma de enseñanza que facilite un aprendizaje dinámico en la interpretación de ECG.
Es por ello que hemos buscado distintos estudios sobre cómo podríamos abordar esta problemática general. Encontramos que, actualmente, se están desarrollando algoritmos de aprendizaje automático para identificar la fibrilación auricular con éxito, lo cual puede ser una opción para solucionar nuestro problema. En la revisión de nuestro estado del arte, descubrimos que ya existen dispositivos que integran el aprendizaje automático para facilitar el diagnóstico de anomalías como la fibrilación auricular (FA); sin embargo, ninguno de ellos está enfocado en la enseñanza como tal.

</p>


# 4. Estado de arte<a name="id4"></a>


# 5. Propuesta de solución<a name="id5"></a>
<p align="justify">
En este contexto, es esencial desarrollar herramientas y dispositivos que faciliten la práctica y el aprendizaje de la interpretación de ECG para profesionales de salud y estudiantes de medicina, especialmente en áreas con recursos limitados como Pasco. El proyecto LECG pretende abordar esta necesidad proporcionando un dispositivo que no solo mide y transmite datos de ECG a un servidor local, sino que también emplea técnicas de aprendizaje automático para identificar posibles anomalías, como la fibrilación auricular. Esto permite a los estudiantes practicar y perfeccionar sus habilidades de diagnóstico.
</p>

# 6. Características técnicas<a name="id6"></a>

El dispositivo LECG presenta las siguientes características técnicas:
* Precisión en la toma de mediciones: Utiliza dos AD8232 para obtener mediciones precisas del ECG del paciente, garantizando que los datos recopilados sean confiables y exactos.
* Transmisión de datos segura: Los datos obtenidos se envían de manera segura a un servidor local, asegurando la privacidad y confidencialidad de la información del paciente.
* Análisis avanzado con aprendizaje automático: En el servidor local, los datos de ECG son analizados mediante técnicas avanzadas de aprendizaje automático, capaces de identificar patrones y anomalías, como la fibrilación auricular.
* Interfaz amigable para el usuario: Los resultados del análisis se presentan de manera clara y comprensible a través de una interfaz intuitiva, permitiendo a los estudiantes visualizar los datos del paciente y recibir recomendaciones sobre posibles diagnósticos.
* Oportunidad de aprendizaje interactivo: Los estudiantes pueden participar activamente en el proceso de aprendizaje, seleccionando la opción de diagnóstico que consideren correcta basada en la información proporcionada. Reciben retroalimentación positiva por respuestas correctas y pueden acumular puntos para su progreso educativo.

En este proyecto, nos enfocaremos en el desarrollo y las capacidades del software (nos enfocamos en los puntos 2, 3, 4 y 5), dado que el diseño y construcción del dispositivo se abordaron en un proyecto separado. 

