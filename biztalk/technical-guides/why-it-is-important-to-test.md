---
title: ¿Por qué es importante para pruebas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91aca5-56d3-4fb8-abe2-af0039804706
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433a5de8d1f90c02c5b06287252b49fd7209e07b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302308"
---
# <a name="why-it-is-important-to-test"></a>¿Por qué es importante para pruebas
Este tema proporciona información general sobre el modo de pensar que conduce a pruebas suficientes, describe los riesgos asociados a un error probar soluciones de BizTalk y se contrasta las dificultades de pruebas manuales con las ventajas de las pruebas automatizadas.  
  
## <a name="testing-as-overhead"></a>Pruebas como "sobrecarga"  
 Por desgracia, con las crecientes demandas de devolución de la inversión (ROI), la fase de prueba de un proyecto se ve a menudo como uno de los aspectos de un plan de proyecto que pueden ser primera escala back.  
  
 Un argumento con pruebas de soluciones de BizTalk es que "no es necesario probar nuestra solución, ya que Microsoft ya exhaustivamente comprueba el servidor BizTalk Server." Si bien es cierto que Microsoft probar exhaustivamente el servidor BizTalk Server, distintos escenarios de uso requieren uno de un número de permutaciones de los requisitos empresariales casi un sinfín de rendimiento, alta disponibilidad, uso de adaptador, latencia, requisitos, de seguimiento uso de la orquestación y código personalizado. Dado que BizTalk Server es extremadamente flexible y puede adaptarse a tantos diferentes escenarios de uso, no simplemente es posible anticipar y de probar todas ellas. Además, se debe optimizar la configuración predeterminada que se aplica en un entorno de BizTalk Server para dar cabida a cada escenario de uso. La única manera de determinar los valores óptimos para un escenario de uso concreto es probar la solución, medir varios parámetros, optimizar el entorno y volver a probar. Considere el siguiente diagrama, que muestra una arquitectura física de ejemplo para una solución de BizTalk Server.  
  
 ![Arquitectura de una implementación de BizTalk Server](../technical-guides/media/5359cf00-e285-4168-a988-8d3b677eb6ba.gif "5359cf00-e285-4168-a988-8d3b677eb6ba")  
Arquitectura física de BizTalk de ejemplo  
  
 Puede ver en el diagrama anterior que la solución de BizTalk Server contiene muchas partes móviles, incluidos varios equipos que ejecuten BizTalk Server, equipos que ejecutan SQL Server, nodos de clúster de servidores y dominios de Active Directory. Después de que el sistema está en funcionamiento, habrá muchos ajustes de configuración aplicadas para optimizar la aplicación por los requisitos empresariales, como para maximizar la rentabilidad de la solución global. Este escenario solo muestra que hay muchas variables en play. Además de la arquitectura física del entorno, considere el siguiente diagrama, que ilustra el flujo de un mensaje a través de BizTalk Server.  
  
 ![Flujo de un mensaje a través de BizTalk Server](../technical-guides/media/dea79a42-5f60-49a1-abdb-870988784ffe.gif "dea79a42-5f60-49a1-abdb-870988784ffe")  
Flujo de mensajes de BizTalk lógicos de ejemplo  
  
 Cuando se observa el diagrama lógico de un mensaje que fluyen a través de BizTalk Server, vemos otras variables que exigen probar por proyecto, incluidos personalizado Enviar y recibir los componentes de canalización y las clases personalizadas que se pueda llamar desde las orquestaciones de BizTalk. Dado que la complejidad de tipo y el uso de componentes personalizados y los componentes de BizTalk varía en cada proyecto, resulta más evidente por qué es importante que realice las pruebas para cada escenario de uso específicos.  
  
## <a name="testing-methodology-and-timelines"></a>Las escalas de tiempo y la misma metodología de prueba  
 Para asegurarse de que las pruebas se realizaron eficaz, el instrumento de prueba debe ser automatizado por completo por lo que se puede reproducir con facilidad y se reduce la posibilidad de errores humanos. Además, debe asignar tiempo suficiente para las pruebas al planear el proyecto. Un enfoque minimalista para pruebas componen requieren pasos manuales similares al siguiente:  
  
1.  Cargar manualmente uno o más mensajes en un punto final de recepción, como la eliminación de un archivo o utilizando un cliente SOAP para llamar a un servicio Web.  
  
2.  Validar manualmente el contenido correcto y la estructura de un mensaje. Como varios esquemas a menudo se encuentran en un proyecto, los mensajes pueden ser una mezcla de archivo sin formato y XML y también pueden contener dependencias de campos cruzados.  
  
    > [!NOTE]  
    >  Un ejemplo de esto sería cualquier proyecto que incluya mensajes de SWIFT. Se trata de mensajes de archivo sin formato que tienen dependencias de campos cruzados. Es decir, un valor de campo depende de otro: validación de XSD simple no realizará la acción aquí; por lo tanto, el Acelerador de SWIFT siguiente utiliza el motor de reglas de BizTalk para la validación de los mensajes. Para obtener más información sobre la [Acelerador de SWIFT](http://go.microsoft.com/fwlink/?LinkID=79657), consulte [Acelerador de SWIFT](http://go.microsoft.com/fwlink/?LinkID=79657) (http://go.microsoft.com/fwlink/?LinkID=79657).  
  
3.  Comprobar manualmente los registros de eventos en los equipos de BizTalk Server para los errores.  
  
4.  Comprobar manualmente las bases de datos BAM (si se utiliza) para validar que la información de la actividad se registra correctamente.  
  
 Mediante un proceso manual como se describió anteriormente para la prueba es subjetivo y es proclive a errores. Considere la posibilidad de tener que examinar un centenar línea mensaje SWIFT con dependencias de campo para los 10 distintos casos de prueba entre. Proyecto la mayoría de los desarrolladores no sería capaz o incluso si se hubieran capaz, ¿no se incline por participar en esta tarea con precisión y fiabilidad. Implementación de un error subjetivo, manual, propenso probar proceso agrega riesgo a un proyecto y aumenta la posibilidad de error.  
  
 El riesgo de error a menudo se amplifica por las escalas de tiempo que no incorporan el tiempo suficiente para las pruebas de planeación del proyecto. Con demasiada frecuencia, un proyecto de prueba bisagras estrategia en un paso de prueba manual único que es programa una semana más o menos antes de la fecha de puesta en marcha. Estas pruebas limitadas coloca el proyecto en peligro. Dados estos una escala de tiempo limitado para las pruebas, si se detecta algún problema, a continuación, el proyecto podría retrasarse porque no se ha asignado ningún tiempo para solucionar problemas. Además, si se detectan y corregir un problema, puede haber suficiente tiempo restante para llevar a cabo pasos de prueba siguiente antes de poner en marcha el sistema.  
  
 La realidad de "única compilación final, paso de prueba individual, toman el proyecto en vivo" es realizar pruebas que suele traducirse en el proyecto que se retrasa, el proyecto a través de presupuesto o incluso peor, el proyecto errores por completo. Para los sistemas de misión crítica, este tipo de la metodología de pruebas es un desastre que tenía que ocurrir.  
  
## <a name="testing-effectively-and-efficiently"></a>Pruebas de forma eficaz y eficiente  
 Porque prueba adecuada a menudo se ve como un lujo costosa en lugar de un requisito entero, con demasiada frecuencia se agregado el final de un proyecto. Dada la complejidad de la pila de software y hardware que se usa en entornos empresariales heterogéneos, este enfoque es poco realista. Implementación de un método de prueba automatizada que puede volver a ejecutar a petición es la mejor manera de probar de forma eficaz y eficiente y es una parte esencial de proyectos con éxito que finalmente proporcionará un excelente rendimiento de la inversión para la empresa. Invirtiendo al principio del proyecto en pruebas funcionales de end-to-end para cada ruta de acceso del código a través del sistema está generando activos de prueba. Estos recursos requieren una inversión (es decir, el tiempo de desarrollo) con el fin de obtener las ventajas de eficacia y una mayor eficacia de prueba más tarde. Para reducir al mínimo la inversión que no será necesario que el proyecto para derivar un marco de trabajo, se recomienda que use el marco de pruebas de carga de Visual Studio 2010. Visual Studio 2010 incluye la mayoría de los pasos de pruebas comunes necesarios para las pruebas correctas y el marco de trabajo que se usan en los escenarios de prueba que se describen más adelante en esta guía.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de las pruebas automatizadas](../technical-guides/implementing-automated-testing.md)