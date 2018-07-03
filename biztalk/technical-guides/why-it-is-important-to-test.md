---
title: Por eso es importante para pruebas | Microsoft Docs
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
ms.openlocfilehash: a74f22813f9752f82985d2e984f5effeb3208e6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009173"
---
# <a name="why-it-is-important-to-test"></a>¿Por qué es importante para la prueba
Este tema se proporciona una visión general de la mentalidad que conduce a pruebas suficientes, se describen los riesgos asociados con errores probar soluciones de BizTalk y contrastan las trampas de las pruebas manuales con las ventajas de las pruebas automatizadas.  
  
## <a name="testing-as-overhead"></a>Las pruebas como "sobrecarga"  
 Desafortunadamente, con cada vez mayores exigencias de rendimiento de la inversión (ROI), la fase de pruebas de un proyecto suele aparecer como uno de los primeros aspectos de un plan de proyecto que se pueden escala back.  
  
 Un argumento frente a las pruebas de soluciones de BizTalk es que "no necesitamos probar nuestra solución, dado que Microsoft ya exhaustivamente prueba BizTalk Server." Si bien es cierto que Microsoft probar exhaustivamente el servidor BizTalk Server, diferentes escenarios de uso requieren uno de un número de permutaciones de los requisitos empresariales casi innumerables para rendimiento, alta disponibilidad, el uso de adaptador, latencia, requisitos, de seguimiento uso de la orquestación y código personalizado. Dado que BizTalk Server es extremadamente flexible y puede adaptarse a muchos escenarios de uso diferentes, no simplemente es posible anticipar y probar todas ellas. Además, se debe optimizar la configuración predeterminada que se aplica en un entorno de BizTalk Server para dar cabida a cada escenario de uso. La única manera de determinar los valores óptimos para un escenario de uso determinado es probar la solución, medir varios parámetros, optimizar el entorno y vuelva a probar. Tenga en cuenta el diagrama siguiente, que describe una arquitectura física de ejemplo para una solución de BizTalk Server.  
  
 ![Arquitectura de una implementación de BizTalk Server](../technical-guides/media/5359cf00-e285-4168-a988-8d3b677eb6ba.gif "5359cf00-e285-4168-a988-8d3b677eb6ba")  
Arquitectura física de BizTalk de ejemplo  
  
 Puede ver en el diagrama anterior que la solución de BizTalk Server contiene muchas partes móviles, incluidos varios equipos que ejecuten BizTalk Server, los equipos que ejecutan SQL Server, nodos de clúster de servidores y dominios de Active Directory. Después de que el sistema está en funcionamiento, habrá muchos ajustes de configuración se aplica para optimizar la aplicación por los requisitos empresariales, como para maximizar la rentabilidad general de la solución. Este escenario solo se muestra que hay muchas variables en play. Además de la arquitectura física del entorno, considere el siguiente diagrama, que ilustra el flujo de un mensaje a través de BizTalk Server.  
  
 ![Flujo de un mensaje a través de BizTalk Server](../technical-guides/media/dea79a42-5f60-49a1-abdb-870988784ffe.gif "dea79a42-5f60-49a1-abdb-870988784ffe")  
Ejemplo de flujo de lógica de mensaje de BizTalk  
  
 Cuando nos centramos en el diagrama lógico de un mensaje fluye a través de BizTalk Server, vemos otras variables que exigen probar por proyecto, incluidos personalizada enviar y recibir los componentes de canalización y las clases personalizadas que pueden llamarse desde las orquestaciones de BizTalk. Dado que la complejidad de tipo y el uso de componentes personalizados y componentes de BizTalk varía en cada proyecto, se vuelve más evidente por qué es importante realizar pruebas para cada escenario de uso específicos.  
  
## <a name="testing-methodology-and-timelines"></a>Escalas de tiempo y la metodología de pruebas  
 Para asegurarse de que las pruebas se realizaron eficiente y eficaz, el agente de prueba debería estar completamente automatizado por lo que se puede reproducir fácilmente y se reduce la posibilidad de errores humanos. Además, es conveniente asignar tiempo suficiente al planear el proyecto de prueba. Un enfoque minimalista a la prueba incluye pasos manuales similares al siguiente:  
  
1. Cargar manualmente uno o más mensajes a un punto de conexión de recepción, como un destino de archivo o mediante un cliente SOAP para llamar a un servicio Web.  
  
2. Validar manualmente el contenido correcto y la estructura de un mensaje. Como varios esquemas a menudo se encuentran en un proyecto, los mensajes pueden ser una mezcla de archivo sin formato y XML y también pueden contener las dependencias de campos cruzados.  
  
   > [!NOTE]  
   >  Un ejemplo de esto sería cualquier proyecto que incluya mensajes de SWIFT. Estos son los mensajes de archivo sin formato que tienen dependencias de campos cruzados. Es decir, el valor de un campo que depende de otro: validación de XSD simple no hará aquí; por lo tanto, el Acelerador de SWIFT hace uso del motor de reglas de BizTalk para la validación de los mensajes. Para obtener más información sobre la [Acelerador de SWIFT](http://go.microsoft.com/fwlink/?LinkID=79657), consulte [Acelerador de SWIFT](http://go.microsoft.com/fwlink/?LinkID=79657) (http://go.microsoft.com/fwlink/?LinkID=79657).  
  
3. Comprobar manualmente los registros de eventos en los equipos de BizTalk Server para los errores.  
  
4. Compruebe manualmente las bases de datos BAM (si se usa) para validar que la información de la actividad se registra correctamente.  
  
   Mediante un proceso manual como se describió anteriormente para la prueba es subjetivo y es propensa a errores. Considere la posibilidad de tener que examinar cien línea mensaje SWIFT con entre las dependencias de campo de 10 casos de prueba diferentes. Proyecto más desarrolladores no sería capaz de o incluso si se hubieran capaz, no serían tentados a participar en esta tarea forma confiable y precisa. Implementación de un error subjetivo, manual, proceso de comprobación propenso riesgo agrega a un proyecto y aumenta la probabilidad de error.  
  
   A menudo se intensifica el riesgo de error mediante escalas de tiempo que no incorporan el tiempo suficiente para las pruebas de planeación del proyecto. Con demasiada frecuencia, un proyecto de pruebas estrategia bisagras en un paso de prueba manual única que está había programada una semana más o menos antes de la fecha de publicación. Estas pruebas limitado coloca el proyecto en peligro. Dado tal una escala de tiempo limitado para las pruebas, si se detecta algún problema, a continuación, el proyecto podría retrasarse porque asignada no tiene tiempo para corregir problemas. Además, si se detecta y se se ha corregido un problema, puede ser suficiente tiempo restante para llevar a cabo pasadas posteriores prueba antes de que el sistema esté activo.  
  
   La realidad de "compilación final único, solo prueba superada, toman el proyecto live" pruebas son que frecuentemente resulta en el proyecto que se retrasa, el proyecto a través de presupuesto o incluso peor, el proyecto con errores por completo! Para sistemas críticos, este tipo de metodología de pruebas es un desastre que tenía que ocurrir.  
  
## <a name="testing-effectively-and-efficiently"></a>Las pruebas de manera eficaz y eficiente  
 Dado que las pruebas correspondientes a menudo se ven como un lujo costoso en lugar de un requisito entero, con demasiada frecuencia se agrega la parte final de un proyecto. Dada la complejidad de la pila de software y hardware utilizada en entornos empresariales heterogéneos, este enfoque no es realista. Implementación de un enfoque de prueba automatizada que puede volver a ejecutar a petición es la mejor manera de probar de manera eficaz y eficiente y es un componente integral de proyectos correctos que en última instancia entregan un ROI excelente para la empresa. Al invertir al principio del proyecto en pruebas funcionales de end-to-end para cada ruta de acceso del código a través del sistema va a generar activos de prueba. Estos recursos requieren la inversión (es decir, el tiempo de desarrollo) con el fin de obtener las ventajas de una mayor eficacia de pruebas y la eficiencia más adelante. Para minimizar la inversión necesaria desde el proyecto para derivar un marco, se recomienda usar el marco de pruebas de carga de Visual Studio 2010. Visual Studio 2010 incluye la mayoría de los pasos de prueba comunes necesarios para realizar una prueba correctamente y es el marco que se utilizan en los escenarios de prueba más adelante en esta guía.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de pruebas automatizadas](../technical-guides/implementing-automated-testing.md)