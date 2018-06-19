---
title: Cómo probar y depurar un adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6563ea-b4ea-4617-b3da-d31250d002ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508f0b5a5ee7b29ed6e2fbde9a94b352d645e550
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256868"
---
# <a name="how-to-test-and-debug-an-adapter"></a>Cómo probar y depurar un adaptador
La depuración de problemas en tiempo de ejecución requiere a menudo llevar a cabo un enfoque desde varias perspectivas. Los datos se deben recopilar de varios orígenes, por ejemplo, el seguimiento del software, los contadores de rendimiento, las entradas del registro de eventos, los eventos de Instrumental de administración de Windows (WMI) y el código de origen de la depuración, con el fin de determinar la causa de los problemas o errores en el software.  
  
 Para depurar un adaptador, éste deberá estar conectado al proceso BtsNtSvc.exe, dado que los adaptadores de recepción y de envío se ejecutan en el espacio de direcciones del servicio de BizTalk. Sin embargo, en el caso de los adaptadores de recepción aislados, el depurador debe estar conectado al proceso que aloja el adaptador.  
  
 El código de tiempo de ejecución del adaptador se debe instrumentalizar con código de seguimiento para capturar diagnósticos en tiempo de ejecución y solucionar problemas. Para ello, puede usar Enterprise Instrumentation Framework (EIF) de Microsoft. Normalmente resulta útil agregar instrucciones de seguimiento para los diferentes niveles de gravedad, tales como realizar el seguimiento únicamente de las condiciones de error, de los errores y las advertencias y, finalmente, realizar el seguimiento de errores, advertencias e instrucciones informativas. Además, puede que los adaptadores más complejos tengan subsistemas independientes para los que es necesario realizar un seguimiento de forma aislada unos de otros. Por ejemplo, un adaptador puede tener un subsistema de red y un subsistema principal. Al habilitar el seguimiento para todos los subsistemas, puede que se genere una cantidad excesiva de "ruido" en algunos casos.  
  
 Se deben agregar contadores de rendimiento para capturar tasas y valores en tiempo de ejecución y aportar más información sobre el comportamiento del adaptador en tiempo de ejecución. Por ejemplo, un adaptador podría publicar contadores de rendimiento para los números sin procesar de mensajes enviados de cada uno de los extremos, además de la tasa de mensajes enviados por segundo.  
  
 Los eventos de WMI también pueden resultar de utilidad en algunos escenarios de error críticos.  Por ejemplo, si un adaptador genera un error crítico que hace que éste cierre una ubicación de recepción, la activación de un evento de WMI permite a un administrador escuchar dicho evento y llevar a cabo la acción necesaria.  
  
## <a name="adapter-testing"></a>Pruebas de adaptadores  
 Al desarrollar un adaptador personalizado para BizTalk Server, recuerde que deberá hacerlo siguiendo los estándares de calidad del software empresarial. Esto significa que debe probar el adaptador exhaustivamente antes de enviarlo. En esta sección, si bien no se describe con total detalle la forma de probar los adaptadores, sí se ofrecen unas pautas de lo que se debe llevar a cabo. En general las pruebas de código en tiempo de ejecución, como adaptadores deben abarcar tres grandes categorías: pruebas funcionales, pruebas de esfuerzo y pruebas de rendimiento.  
  
### <a name="function-testing"></a>Pruebas funcionales  
 El adaptador se debe probar para todas las permutaciones de su funcionalidad, incluidas tanto las pruebas positivas como las negativas. Las pruebas positivas deberían incluir al menos los siguientes escenarios:  
  
-   Recibir mensajes  
  
-   Transmitir mensajes  
  
-   Transmitir un mensaje mediante un puerto dinámico  
  
-   Deshabilitar ubicaciones de recepción  
  
-   Actualizar la configuración  
  
-   Asegurar que las ventanas de servicio funcionan tanto en los adaptadores de recepción como en los de envío  
  
-   Asegurar la integridad transaccional de los adaptadores con transacciones  
  
 Las pruebas negativas deberían incluir, entre otras:  
  
-   Recibir mensajes no válidos  
  
-   Recibir un lote mixto de mensajes, algunos válidos y otros no válidos  
  
-   Transmitir error  
  
-   Reintentar con éxito  
  
-   Si se produce un error en el reintento, pasar al siguiente transporte con éxito  
  
-   Si se produce un error en el traslado al siguiente transporte, suspender el mensaje  
  
-   Transmitir un lote mixto de mensajes  
  
-   Conmutación por error de la base de datos  
  
### <a name="stress-testing"></a>Pruebas de esfuerzo  
 Los adaptadores son componentes de tiempo de ejecución, y como tales deben cumplir con los rigurosos requisitos del software de tiempo de ejecución. Generalmente, las pruebas de esfuerzo se llevan a cabo mediante la ejecución de escenarios bajo carga durante un período de tiempo. Además se deberían realizar pruebas de errores entre el tiempo medio de alto esfuerzo y de bajo esfuerzo, en el que el adaptador se ejecuta bajo carga durante un período de tiempo determinado.  
  
 Por citar algunas directrices generales para estas pruebas, podríamos indicar que el adaptador se ejecute a alto esfuerzo durante 72 horas aproximadamente, donde el número de mensajes a través del adaptador produzca una utilización de la CPU de en torno al 80 o 90 por ciento. En una situación de bajo esfuerzo, la utilización de la CPU estaría en torno al 30 o 40 por ciento durante aproximadamente 120 horas.  
  
### <a name="performance-testing"></a>Pruebas de rendimiento  
 Los adaptadores se deben desarrollar teniendo en cuenta el rendimiento. Antes de lanzar un adaptador, debería validar su rendimiento. Es importante garantizar que su rendimiento se escale horizontal y verticalmente, es decir, al agregar más CPU se produce un aumento del rendimiento del mismo modo que al agregar más equipos. La generación de perfiles del código permite eliminar los cuellos de botella del rendimiento.