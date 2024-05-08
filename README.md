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
8. [Caja negra](#id8)
9. [Estructura de funciones](#id9)
10. [Diagrama de bloques](#id10)
11. [Matriz morfológica](#id11)
12. [Alternativas de solución](#id12)
13. [Esquemáticos](#id13)
14. [Diseño de PCDB](#id14)
15. [Integrantes](#id15)
16. [Docentes del curso](#id16)
17. [Referencias bibliográficas](#id17)
   
***

# 1. Introducción<a name="id1"></a>

<p align="justify">
En cada latido, el corazón se despolariza para desencadenar su contracción. Esta actividad eléctrica se transmite por todo el cuerpo y puede ser captada en la piel. Este es el principio detrás del electrocardiograma (ECG). Una máquina de ECG registra esta actividad a través de electrodos en la piel y la muestra gráficamente. Un ECG implica la conexión de 10 a 12  cables eléctricos al cuerpo: uno a cada miembro y seis a través del pecho.[13]
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

</p>



# 3.  Problemática<a name="id3"></a>

## 3.1 Problemática general

<p align="justify">
La escasez de especialistas en cardiología capacitados para interpretar electrocardiogramas (ECG) en la región Pasco dificulta el diagnóstico y posterior tratamiento oportuno de enfermedades cardiacas.
</p>

# 3.2 Problemática específica

<p align="justify">
La falta de herramientas tecnológicas que integren el potencial del Machine Learning y el aprendizaje automático para capacitar a más especialistas en cardiología en la interpretación de electrocardiogramas (ECG) en la región Pasco, plantea un desafío crítico en el diagnóstico y posteriormente en el tratamiento oportuno de enfermedades cardiacas.
</p>


# 4. Estado de arte<a name="id4"></a>


# 5. Propuesta de solución<a name="id5"></a>


# 6. Características técnicas<a name="id6"></a>
