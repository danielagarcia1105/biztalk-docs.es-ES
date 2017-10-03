---
title: "Ejecutar el ejemplo de servicio de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9d7e3e4d4bce4e46653f7b650004928368eced
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-resolver-service-sample"></a>Ejecutar el ejemplo de servicio de resolución
El ejemplo de servicio de resolución muestra los siguientes escenarios:  
  
-   Resolver un URI de UDDI3 con una clave de enlace del extremo de servicio  
  
-   Resolver un URI de UDDI3 mediante una búsqueda de categorización del extremo de servicio  
  
-   Resolver una transformación (tipo de asignación de BizTalk) con una resolución estática  
  
-   Resolver un URI con una resolución estática del extremo de servicio  
  
-   Resolver un URI con una expresión XPath del extremo de servicio  
  
-   Resolver un itinerario mediante un solucionador de itinerario estático  
  
-   Resolver un itinerario mediante un solucionador de itinerario ESTÁTICOS (Unity)  
  
-   Resolver un itinerario mediante BRE (BRI resolución)  
  
-   Resolver un itinerario mediante BRE (resolución BRI) con el mensaje  
  
-   Resolver un URI del extremo de servicio con el BRE  
  
-   Resolver una transformación mediante BRE  
  
 **Para ejecutar todos los escenarios de resolución mediante la implementación de ASMX del servicio de resolución**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_ASMX.cmd.  
  
3.  Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.  
  
 **Para ejecutar todos los escenarios de resolución mediante la implementación de WCF del servicio de resolución**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_WCF.cmd.  
  
3.  Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.