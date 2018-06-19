---
title: Limitaciones y los requisitos de servicio de mensajes TIBCO Enterprise | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcd386245ba06c2e3b5a5b92df7b7a7f01a1a749
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013675"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a>Requisitos y limitaciones de TIBCO Enterprise Message Service

## <a name="system-requirements"></a>Requisitos del sistema  
Incluido con TIBCO Enterprise Message Service incluye un cliente SDK (mediante la API TIBCO EMS C#). El adaptador de BizTalk para TIBCO EMS usa esta API para comunicarse con TIBCO EMS.  
  
## <a name="add-the-api-to-the-gac"></a>Agregar la API a la GAC  
 El adaptador de BizTalk para TIBCO EMS requiere que la API de TIBCO EMS C#, TIBCO.EMS.dll, se agregue a la memoria caché global de ensamblados (GAC). El adaptador desencadena una excepción y registra un mensaje adecuado si este ensamblado no está instalado.  
  
1.  Copie la API de TIBCO EMS C# en el equipo que tenga [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado.  
  
2.  Cambie los directorios a la ubicación del archivo de la API de C#, TIBCO.EMS.DLL.  
  
     En la instalación predeterminada, la ruta de acceso a esta DLL es c:\tibco\ems\clients\cs\TIBCO.EMS.DLL.  
  
3.  En un símbolo del sistema, escriba:  
  
     `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
     El archivo TIBCO.EMS.dll ahora muestra la memoria GAC.  
  
     Para ver la lista GAC, en el Panel de Control, abra **herramientas administrativas**, abra **Microsoft .NET Framework X.XConfiguration**y, a continuación, haga clic en **caché de ensamblados**.  
  
## <a name="limitations"></a>Limitaciones  
 El adaptador de BizTalk para TIBCO Enterprise Message Service usa TIBCO.EMS.dll para comunicarse con TIBCO Enterprise Message Service. Cuando se usa la API TIBCO EMS C#, se deben tener en cuenta las siguientes limitaciones:  
  
-   La compresión de mensajes, que permite al cliente de TIBCO EMS enviar a EMS mensajes de forma comprimida, no se encuentra disponible con la API de C#.  
  
-   El cifrado de mensajes entre el adaptador y el servidor no se encuentra disponible con la API de C#. La API de C# no permite el cifrado de SSL mediante las bibliotecas OpenSSL.  
  
-   La API de C# no es compatible con la API de administración para EMS.  
  
-   No se pueden enviar ni recibir mensajes de más de 50 MB mediante el adaptador de BizTalk TIBCO EMS. Por encima de este tamaño, el entorno experimenta excepciones System.OutOfMemoryException.  
  
## <a name="see-also"></a>Vea también  
 [Planificación y arquitectura](../core/planning-and-architecture16.md)