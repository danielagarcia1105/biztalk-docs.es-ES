---
title: Ejecución del ejemplo de servicio de resolución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c569f0be544292b4a70d49f4c75a038e2fed65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006677"
---
# <a name="running-the-resolver-service-sample"></a>Ejecución del ejemplo de servicio de resolución
El ejemplo de servicio de resolución muestra los siguientes escenarios:  

- Resolver un URI de UDDI3 mediante una clave de enlace del extremo de servicio  

- Resolver un URI de UDDI3 mediante una búsqueda de categorización del extremo de servicio  

- Resolver una transformación (tipo de asignación de BizTalk) con una resolución estática  

- Resolver un punto de conexión de servicio URI con una resolución estática  

- Resolver un punto de conexión de servicio URI utilizando una expresión XPath  

- Resolver un itinerario mediante una resolución estática de itinerario  

- Resolver un itinerario mediante un solucionador de itinerario estático (Unity)  

- Resolver un itinerario mediante BRE (BRI resolución)  

- Resolver un itinerario mediante BRE (resolución BRI) con el mensaje  

- Resolver un identificador URI del extremo de servicio con el BRE  

- Resolver una transformación mediante BRE  

  **Para ejecutar todos los escenarios de resolución mediante la implementación de ASMX, el servicio de resolución**  

1. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de Microsoft BizTalk para iniciarlo.  

2. En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_ASMX.cmd.  

3. Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.  

   **Para ejecutar todos los escenarios de resolución mediante la implementación de WCF del servicio de resolución**  

4. Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de BizTalk para iniciarlo.  

5. En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService y, a continuación, haga doble clic en el archivo RunTestClient_WCF.cmd.  

6. Abra la carpeta \Source\Samples\ResolverService\Output y, a continuación, abra los archivos de resultados, que corresponden a las solicitudes de resolución enumeradas anteriormente.
