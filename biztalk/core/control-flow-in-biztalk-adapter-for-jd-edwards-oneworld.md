---
title: Controlar el flujo en el adaptador de BizTalk para JD Edwards OneWorld | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc5a8be6516b61c4049242952967ce939513e9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237980"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a>Control del flujo del adaptador de BizTalk para JD Edwards OneWorld
En este tema se tratan los flujos de control de tiempo de diseño y de tiempo de ejecución en el Adaptador de Microsoft BizTalk para JD Edwards OneWorld.  
  
## <a name="design-time-flow"></a>Flujo de tiempo de diseño  
 Cuando se abre el adaptador (usando las credenciales y la información del sistema del cuadro de diálogo Propiedades de transporte), una o varias instancias de la función empresarial de la aplicación JD Edwards OneWorld se crean y agrupan. Al examinar el espacio de nombres en el Asistente para el adaptador, aparece una lista de funciones empresariales. Al hacer clic en una función empresarial se muestran sus métodos lógicos junto con las firmas de métodos.  
  
## <a name="run-time-flow"></a>Flujo de tiempo de ejecución  
 Las instancias de la función empresarial de JD Edwards OneWorld se crean y agrupan para cada subproceso. Cuando se envía una llamada de método a un servicio empresarial, los metadatos del método se leen usando la función empresarial de la aplicación JD Edwards OneWorld; sin embargo si los metadatos del método ya se han almacenado en caché, la función empresarial usará la información almacenada en caché y realizará una llamada al método correspondiente. En tiempo de ejecución, una capa de interfaz de JD Edwards OneWorld se construye dinámicamente. A través de la capa de interfaz, el Adaptador de BizTalk para JD Edwards OneWorld admite la invocación y las conversiones de datos.  
  
 El Adaptador de BizTalk para JD Edwards OneWorld asigna descripciones de interfaz de las firmas del método de la aplicación JD Edwards OneWorld, permitiendo a BizTalk Server interactuar con estas descripciones de interfaz.  
  
 El adaptador habilita las aplicaciones de la empresa para que interactúen con la aplicación JD Edwards OneWorld extendiendo las funciones desde la aplicación en forma de uno o varios de los siguientes:  
  
-   Formatos de datos nativos  
  
-   Procedimientos  
  
-   Métodos  
  
-   Mensajes  
  
-   Propiedades  
  
-   Interfaces de aplicación  
  
 En tiempo de ejecución, el adaptador de BizTalk para JD Edwards OneWorld benera interfaces de aplicación para las aplicaciones cliente que interactúan con JD Edwards OneWorld. El adaptador puede crear, eliminar e invocar objetos empresariales según sea necesario, para realizar cálculos en la aplicación e invocar métodos directamente. Todas las llamadas a JD Edwards OneWorld son llamadas sincrónicas. El adaptador recibe los mensajes XML desde BizTalk Server, incluye los mensajes en un sobre SOAP y transforma los datos para la llamada desde mensajes SOAP a tipos de Java.  
  
 La respuesta se devuelve siguiendo un proceso similar:  
  
1.  Los tipos de Java se transforman en mensajes SOAP.  
  
2.  Los mensajes SOAP se convierten en mensajes XML.  
  
3.  Los mensajes XML se envían a BizTalk Server para su posterior procesamiento.  
  
### <a name="apartment-threading-of-business-functions"></a>Apartamento de subproceso de funciones empresariales  
 Una función empresarial de JD Edwards OneWorld, en cualquier instancia, solo puede usarse en el subproceso donde se creó u obtuvo. Esto se conoce como *apartamento de subproceso*. El marco de agrupación de conexiones del adaptador de BizTalk para JD Edwards OneWorld administra un grupo de conexiones disponibles.  
  
### <a name="connection-pooling"></a>Agrupar conexiones  
 La agrupación de conexioens mejora el rendimiento de llamadas manteniendo las conexiones a los sistemas del servidor abiertas y reusándolas en lugar de cerrarlas después de cada llamada. El adaptador de BizTalk para JD Edwards OneWorld le permite agrupar conexiones dentro de determinados ID de inicio de sesión, pero manteniendo un control crítico del número total de conexiones en todas las agrupaciones.  
  
 Cualquier nueva instancia de función empresarial usa el subproceso en el cual se creó y la instancia se destruyó después de cada operación. Todas las llamadas de JD Edwards OneWorld a funciones empresariales son sin estado; no obstante, durante la operación, el adaptador se asegura de que la función empresarial se use en el subproceso correcto.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones](../core/developing-applications3.md)   
 [Planeamiento y arquitectura](../core/planning-and-architecture17.md)