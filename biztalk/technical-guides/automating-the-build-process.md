---
title: "Automatizar el proceso de compilación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 995dac20-82a1-46ed-b8a3-0aa6182cb821
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d62380146f0bfba188843ed0e022340d88fcaceb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="automating-the-build-process"></a>Automatizar el proceso de compilación
Un proceso automatizado de compilación compila, implementa y, a continuación, ejecuta pruebas de comprobación de la compilación (BVT) en el código fuente más reciente para un proyecto a intervalos regulares, predeterminados. A continuación, un "informe de compilación", que detalla el éxito o error del proceso de compilación, se difunde a las partes interesadas del proyecto. El informe de generación se analiza para determinar qué áreas del proyecto necesitan atención y si el proyecto debe puede revertir a una versión anterior.  
  
 La eficacia de un proceso automatizado de compilación es que puede programarse para ejecutarse durante "desactivar horas". De este modo, también puede ayudar a asegurar la estabilidad del proyecto sin realizar ciclos directamente fuera el tiempo de desarrollo.   
 En este tema se proporciona información general del proceso de compilación, describe cómo pruebas de comprobación de compilación se integra en el proceso de compilación, se describe aspectos de las pruebas funcionales utilizar durante las pruebas de comprobación de compilación y proporciona información acerca de la importancia de automatizar el proceso de compilación.  
  
## <a name="overview-of-the-build-process"></a>Información general del proceso de compilación  
 Antes de buscar en los detalles de las pruebas, es importante tener en cuenta el contexto de cómo probar encaja en el proceso de compilación general. Todos los grupos de productos de Microsoft funcionan de la filosofía de que el proceso de compilación es el pulso de cualquier proyecto de software. Este enfoque también se usa por muchos de la parte superior de todo el mundo consultoría las empresas que desarrollan soluciones de misión crítica en la pila de software de Microsoft. Sin un latido constante y una comprobación regular del mismo, es imposible conocer el estado del proyecto. Para asegurarse de que los grupos de productos tengan una visión continua del estado general del proyecto, el proceso de compilación se ejecuta a diario, por lo general a medianoche. Los pasos siguientes resumen un proceso automatizado de compilación típico:  
  
1.  Obtener la última compilación de código fuente desde el repositorio de código fuente.  
  
2.  Compilar el código fuente.  
  
3.  Módulo de seguridad de los archivos binarios para la implementación – normalmente con las secuencias de comandos o archivos de Microsoft Windows Installer.  
  
4.  Implementar el proyecto en un servidor de prueba.  
  
5.  Ejecutar automáticamente un conjunto completo de pruebas de comprobación de la compilación (BVT).  
  
6.  Publicar un informe de generación detallado a los miembros del equipo del proyecto.  
  
> [!NOTE]  
>  Pruebas BVT son pruebas funcionales que utilicen las características principales de la solución para probar su calidad.  Debe asegurarse de que sus pruebas BVT son lo suficientemente exhaustivos para medir la calidad de compilación, pero un valor suficientemente pequeño que se ejecutan dentro del tiempo de compilación diaria asignado.  
  
> [!NOTE]  
>  También debería tratar como parte del proyecto de software con fines de prueba de implementación, anular la implementación, configuración e instalación de secuencias de comandos o procesos. Las operaciones de proyecto, así como la implementación y configuración del mismo, deberán probarse.  
  
 Este proceso se completa normalmente temprano aproximadamente 6 A.M., lo que permite a los primeros miembros del equipo empezar a trabajar en la compilación del día nuevo. Si el error de uno o más de las pruebas BVT de la noche anterior, es responsabilidad del equipo para corregirlo tan pronto como sea posible.  
  
 Después de un proceso de compilación diaria tiene muchas ventajas para el proyecto. En primer lugar, proporciona un latido regular (formado por la compilación diaria además de las pruebas automatizadas BVT). En segundo lugar, si se utiliza pruebas BVT fuerza la integración con sistemas que es una tarea difícil y hacerlo al principio de por sí reduce los riesgos del proyecto. Debido al tiempo necesario para completarlos, se suelen realizar pruebas de rendimiento y esfuerzo fuera del proceso de compilación diaria. Pruebas de rendimiento y esfuerzo normalmente están programadas para realizarse en una compilación de hito en el proyecto.  
  
 El proceso de compilación diaria puede ser y se ha utilizado, muy eficazmente en soluciones de BizTalk. Sin embargo, debe asegurarse de las tareas que se suelen dejar al final en los proyectos de se realizan de forma iterativa desde el principio. Por ejemplo, la implementación de BizTalk Server es ciertamente no trivial. Es importante que los scripts de implementación automatizada se desarrollado por adelantado. Si no lo hace, podrá finalizar la implementación manual y sin implementar la solución muchas veces a lo largo del proyecto, que cuestan más tiempo al final. Hay herramientas disponibles para controlar el proceso de compilación diaria; Visual Studio Team System y Team Foundation Server son la opción principal para muchas personas. Scripts de MSBuild pueden utilizarse para controlar los pasos del proceso de compilación. Otra alternativa es el código abierto [CruiseControl.NET herramienta](http://go.microsoft.com/fwlink/?LinkId=116093) (http://go.microsoft.com/fwlink/?LinkId=116093).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no otorga ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
 Para obtener más información acerca de la automatización de pruebas mediante Microsoft Test manager, vea el tema [Running Automated Tests](http://go.microsoft.com/fwlink/?LinkID=208368) (http://go.microsoft.com/fwlink/?LinkID=208368) en la documentación en línea de Visual Studio 2010  
  
 Para obtener más información acerca de cómo automatizar el proceso de compilación con Visual Studio 2010, vea [compilar la aplicación](http://go.microsoft.com/fwlink/?LinkID=208369) (HYPERLINK "http://go.microsoft.com/fwlink/? LinkID = 208369" http://go.microsoft.com/fwlink/? LinkID = 208369) en la documentación de Visual Studio 2010.  
  
## <a name="build-verification-testing"></a>Crear pruebas de comprobación  
 Pruebas de comprobación de compilación normalmente consta de los siguientes elementos:  
  
-   **Pruebas unitarias** -porque las pruebas unitarias son normalmente las primeras pruebas para que se desarrolle, lo ideal es que se debe crear antes de que realmente se ha escrito el código, si realmente se usa un enfoque de desarrollo controlado por pruebas. Agregándolos en pruebas BVT durante las primeras etapas de un proyecto, se proporciona al menos algunas cobertura de código inmediatamente. Como el número de pruebas funcionales y, por lo que aumenta la cobertura de pruebas, puede optar por quitar pruebas unitarias de las pruebas BVT.  
  
-   **Pruebas de humo** -to-end pruebas funcionales que probar la funcionalidad básica de la solución. Si estos fallan, algo va mal en serio. Estos normalmente se pueden ejecutar relativamente rápidamente.  
  
-   **Pruebas funcionales** : estos escenarios de extremo a extremo de destino también, pero en este caso se prueban todos los escenarios en el proyecto. Para proyectos grandes puede tener sentido para categorizar aún más las pruebas funcionales (por ejemplo, para habilitar un componente determinado se va a probar rápidamente, confiable y de forma aislada). Una vez haya firmado en la solución como funcionalmente correcta, se deben bloquear estas pruebas funcionales.  
  
-   **Pruebas de comprobación de regresión** : cada vez que un error de la solución se encuentren y corrijan, comprobación de regresión se debe agregar casos de prueba para comprobar que se ha corregido el error y que no es introducirse más adelante en el ciclo de vida del proyecto.  Estas pruebas normalmente será casos que no se tratan en los casos de prueba funcionales. Debe esperar que las pruebas de comprobación de regresión aumentará en número incluso después de que la solución se ha salido en vivo, si se detectan y corrijan errores.  
  
 En proyectos muy grandes, debe hacer sus pruebas BVT un subconjunto del conjunto de pruebas completa funcional (debido a la longitud de tiempo que tardan en ejecutarse). Para los proyectos más pequeños, pruebas BVT conformarán todo el conjunto. Obviamente, si va a integrar las BVT como parte de la compilación diaria, todo el proceso debe ser automatizada. En el resto de este tema, nos centraremos en cómo se pueden utilizar BizUnit y otras herramientas para lograr esto.  
  
## <a name="functional-testing"></a>Pruebas funcionales  
 En el contexto de pruebas funcionales de las aplicaciones de BizTalk, probar un escenario de extremo a extremo concreto. Al realizar este tipo de prueba, es útil imaginar BizTalk Server como un cuadro negro que probar funcionalmente desde una perspectiva externa. Por ejemplo, una prueba puede conllevar incorpore un mensaje de entrada (con los valores conocidos) a un extremo de la ubicación de recepción (para la ubicación del ejemplo, dirección URL, FTP, lo que sea su elección de transporte). La prueba, a continuación, supervisan el número correcto de mensajes con los resultados correctos en el que se genera en el lado de envío. Esto puede parecer bastante sencillo. Sin embargo, cuando se tenga en cuenta que algunos escenarios requieren entradas a estar en un orden determinado y en un momento determinado, y esto compuesta con otros requisitos de la solución (como por ejemplo, cuando se registran los datos de seguimiento de BAM), queda claro que se pueden usadas para una herramienta y el marco de trabajo orquestar esto.  
  
 Es fundamental que las pruebas funcionales está diseñada para cubrir todas las rutas posibles a través de la solución. Esto debe incluir no sólo los escenarios esperados en producción, pero también el error ni rutas de control de excepciones ha implementado, pero nunca pretende utilizar: una frase utilizada normalmente para describir esto es probar "escenario de un mal día". Debe asegurarse de todas las orquestaciones, todos los tipos de mensaje permitidos y todas las ramas de código se ha ejecutado por el conjunto de pruebas funcionales. Las siguientes secciones describen desarrollar positivos y negativos casos de pruebas funcionales para cubrir todas las rutas de código.  
  
 Para obtener más información acerca de las pruebas funcionales y las otras categorías de pruebas que se deben implementar antes de colocar una solución de BizTalk Server al entorno de producción, consulte el tema [lista de comprobación: preparación operativa pruebas](http://go.microsoft.com/fwlink/?LinkId=160138) en el Guía de operaciones de BizTalk Server 2010 en [http://go.microsoft.com/fwlink/?LinkId=160138](http://go.microsoft.com/fwlink/?LinkId=160138).  
  
### <a name="positive-tests"></a>Pruebas positivas  
  
-   Es importante al realizar pruebas positivas para asegurarse de todas las combinaciones de mensajes, canalizaciones, orquestaciones y los puntos de conexión se pasan a través de la solución para que se ha ejecutado todos los flujos de mensajes. Para asegurarse de que prueba todo el código de las rutas de acceso probablemente requerirá que procesar mensajes diferentes con contenido diferente.  
  
-   Al realizar pruebas, use el tipo de transporte que se usará en producción. Por desgracia, con demasiada frecuencia, las pruebas funcionales se realizan únicamente mediante el adaptador de archivo cuando algunos otros tipos de transporte se usará en producción. Adoptar este enfoque consiste en configurar y el proyecto general por error más adelante.  
  
-   Validar la carga de todos los mensajes que se envían desde el sistema. Si los mensajes XML, debe validar su esquema y los campos de clave en el mensaje con expresiones XPath.  
  
-   Validar los datos de seguimiento almacenados en BAM (si se utiliza); cualquier otro dato que se deja en repositorios de datos externos debe tenerse en cuenta.  
  
-   Probar la ejecución de todas las reglas y directivas del motor de reglas de negocios (BRE) si su solución utiliza BRE.  
  
### <a name="negative-tests"></a>Pruebas negativas  
  
-   Asegúrese de que probar el control de mensajes no válidos a través del sistema. Debe comprobar que la estrategia elegida (para rechazarlos antes de venir en BizTalk Server o suspender ellos) ha funcionado correctamente.  
  
-   Al probar el control de mensajes no válidos, asegúrese de que probar que se han implementado las orquestaciones de control de errores de recepción para controlar los mensajes suspendidos.  
  
-   Asegúrese de que los escenarios de error cubran todos los bloques de excepción en las orquestaciones.  No puede probar esto adecuadamente es un problema común.  
  
-   Si utiliza transacciones de larga ejecución con el comportamiento de compensación, pruebe cuidadosamente estos escenarios. Se trata de otra área donde pruebas inadecuadas, le cobrará consecuencias graves en un entorno de producción.  
  
-   Asegúrese de que los errores se registran correctamente en los registros de error adecuado.  
  
## <a name="automation-is-key"></a>Automatización es clave  
 Para hacer todo esto de forma eficaz, invierta el tiempo por adelantado para automatizar las pruebas. Pruebas manuales resulta lento, error propensa a y costoso (en términos de tiempo y el costo). Cada vez que realiza un paso de prueba manual, agregue otro lote de tareas que deben ser controlada por recursos del proyecto (personas en el equipo). Al automatizar por adelantado, es posible obtener un retorno de la inversión inicial que se requiere para desarrollar las pruebas cada vez que se ejecutan. Deben ejecutar de forma rápida y eficaz y ser repetible; buenas pruebas funcionales cada prueba también debe ser autónomo (debe ser independiente de cualquier otro; adoptar este enfoque le permite ejecutar varias pruebas secuencialmente como un conjunto de pruebas). Las pruebas funcionales siempre deben producir el mismo resultado. Pruebas funcionales mal escritas o código mal escrito producirá resultados de pruebas diferentes entre ejecuciones de pruebas, dando lugar a confusión y pérdida de tiempo investigar la causa del error.  
  
 Es importante minimizar el esfuerzo de desarrollo necesario para escribir cada prueba funcional. Por lo general, cuanto más caro resulta algo (en términos de tiempo de desarrollo), generan menos casos de prueba es probable que terminen con. Esto significa que tendrá un menor nivel de cobertura de pruebas en el código. Mediante el uso de un marco de pruebas, puede desarrollar casos de prueba y agiliza y, por lo tanto, resulte más fácil obtener cobertura de código completo. La mayoría de los marcos de pruebas buena utilizan un enfoque declarativo para definir pruebas. (Es decir, la configuración de una prueba se almacena en un archivo de configuración, que normalmente es un archivo XML). Uso de una buena manera de comprobar framework permite desarrollar una completa funcional conjunto de pruebas de una manera ágil y confiable y evita tener que volver a "inventar la rueda" una y otra vez, por lo que decirlo.  
  
## <a name="msbuild-support-for-biztalk-server-projects"></a>Compatibilidad para MSBUILD para proyectos de BizTalk Server  
 BizTalk Server proporciona compatibilidad para la plataforma de motor de compilación de Microsoft (MSBUILD), lo que permite la creación de proyectos administrados en entornos de laboratorio de compilación donde no está instalado Visual Studio. MSBUILD permite compilar proyectos desde una línea de comandos y la funcionalidad avanzada que incluye MSBUILD, registro y el procesamiento por lotes. Para obtener más información acerca de MSBUILD, vea [información general sobre MSBuild](http://go.microsoft.com/fwlink/?LinkId=131739) (http://go.microsoft.com/fwlink/?LinkId=131739).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de pruebas automatizadas](../technical-guides/implementing-automated-testing.md)