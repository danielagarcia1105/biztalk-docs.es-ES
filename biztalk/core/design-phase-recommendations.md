---
title: "Recomendaciones para la fase de diseño | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3d183e-a6f3-47d0-90ac-99b12c064607
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0f361734aa7539f12940212a339b582bb4f2641
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="design-phase-recommendations"></a>Recomendaciones de la fase de diseño
Los entregables principales de la fase de diseño son las especificaciones de diseño de los casos del sistema y de prueba para validar la funcionalidad y el rendimiento del sistema. Las investigaciones sobre la viabilidad de las características y las pruebas son una parte habitual del proceso de diseño, que comprende el desarrollo inicial y, en el caso del diseño de validación, algunas pruebas anticipadas de implementaciones de prueba de concepto, tal como se describe abajo en esta sección.  
  
## <a name="acquire-detailed-throughput-and-latency-profiles"></a>Obtener perfiles detallados de rendimiento y latencia  
 A partir de los perfiles iniciales de carga sobre los que se establecieron los criterios de versión de rendimiento de la fase anterior del proyecto, establezca perfiles detallados de rendimiento y latencia durante la fase de diseño. Obtenga datos de rendimiento, si hay alguno, de sistemas de producción. El uso de datos de producción proporcionará perfiles de rendimiento realistas sobre los que se pueden diseñar casos de prueba durante esta fase. Si no hay datos de producción disponibles, se debe extrapolar un perfil realista a partir de la carga esperada.  
  
 Es fundamental que los casos de prueba de rendimiento creados durante la fase de diseño incluyan perfiles de rendimiento que emulen de forma rigurosa la carga que previsiblemente deberá tolerar el sistema en producción. Para obtener más información acerca de cómo crear perfiles de rendimiento realistas y sostenibles, consulte [¿qué es rendimiento sostenible?](../core/what-is-sustainable-performance.md)  
  
## <a name="investigate-performance-risk-mitigations"></a>Investigar formas de mitigar los riesgos relacionados con el rendimiento  
 Durante la fase de requisitos, se identificaron los riesgos asociados a la consecución de los objetivos de rendimiento deseados, así como las posibles mitigaciones.  Los riesgos y las mitigaciones se deben investigar lo antes posible en la fase de diseño para que haya tiempo de cambiar el diseño si es necesario. Para cada riesgo identificado, se deben realizar pruebas de prueba de concepto (POC) con el fin de demostrar que el riesgo constituye un problema; posteriormente, se deben probar las mitigaciones para evaluar su eficacia.  
  
 Por ejemplo, supongamos que un sistema heredado usa FTP para comunicarse con otros sistemas. Al examinar el nivel de rendimiento que puede alcanzar el servidor FTP heredado en combinación con el adaptador de FTP de BizTalk Server, se pone de manifiesto que el rendimiento deseado (establecido como criterio de versión durante la fase de requisitos) no se podrá alcanzar. Para mitigar el riesgo en el proyecto, se identifican las siguientes alternativas durante la fase de requisitos:  
  
-   Escalar vertical u horizontalmente el servidor FTP y crear varias direcciones FTP lógicas dedicadas a tipos de mensajes específicos para distribuir la carga  
  
-   Modificar el sistema heredado para entregar muchos mensajes en un único archivo como un lote, con el fin de reducir la sobrecarga de transferencia por mensaje  
  
-   Modificar el sistema heredado para usar un protocolo alternativo que se sepa que es más rápido que FTP; por ejemplo, MSMQ  
  
 La primera investigación que se debe efectuar en este ejemplo consiste en demostrar que existe el riesgo, para lo cual se probará el rendimiento actual del sistema FTP. Se creará e implementará una solución sencilla de prueba de concepto que únicamente reciba mensajes del servidor FTP. Posteriormente, se aplicará a la solución el perfil de carga de producción que se espera para la ruta FTP. Si el servidor es capaz de tolerar la carga deseada, significa que no existe tal riesgo y, por tanto, no es necesaria ninguna investigación adicional. En caso de que no la tolere, se debe realizar una investigación de prueba de concepto para hallar la alternativa que tiene más probabilidades de solucionar el problema y que supone menos costos y riesgos para el proyecto.  
  
## <a name="refine-system-size-estimate"></a>Mejorar la estimación de tamaño del sistema  
 Las investigaciones realizadas durante la fase de diseño ofrecen información empírica valiosa sobre las capacidades de rendimiento del sistema.  
  
 Consideremos nuevamente el ejemplo anterior, donde se ha demostrado que el rendimiento de FTP es demasiado bajo. Puesto que el entorno ya incluye sistemas que usan MSMQ como transporte de mensajería, se decidió modificar el sistema heredado para utilizar también MSMQ. Sin embargo, durante las pruebas de rendimiento de una nueva prueba de concepto que emplea MSMQ, se observa que la CPU del servidor SQL Server donde reside la base de datos de cuadro de mensajes tiene, de forma casi constante, un nivel de utilización del 100 %, por lo que no se puede alcanzar el rendimiento esperado en la ruta de MSMQ.  
  
 Si se supone que la configuración de SQL Server es óptima para la aplicación, el tamaño del hardware de SQL Server es claramente inferior al necesario para el rendimiento deseado y, por tanto, se debe mejorar el tamaño del sistema. En este caso, el hardware de SQL Server necesita CPU adicionales, CPU más rápidas o ambas cosas.  
  
## <a name="see-also"></a>Vea también  
 [Recomendaciones de planeación del proyecto por fases](../core/project-planning-recommendations-by-phase.md)   
 [Recomendaciones de la fase de requisitos](../core/requirements-phase-recommendations.md)   
 [Recomendaciones de la fase de implementación](../core/implementation-phase-recommendations.md)   
 [Recomendaciones de la fase de comprobación](../core/verification-phase-recommendations.md)   
 [Recomendaciones para la fase versión](../core/release-phase-recommendations.md)