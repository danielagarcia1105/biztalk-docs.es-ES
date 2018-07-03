---
title: Desarrollar adaptadores personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f901800cb1d7426a364a87b0f3f915d8436244
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022562"
---
# <a name="developing-custom-adapters"></a>Desarrollar adaptadores personalizados
Para intercambiar mensajes con sistemas externos, aplicaciones y entidades, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el concepto de un adaptador. Los adaptadores son COM o [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] componentes que transfieren mensajes desde y hacia el final de la empresa. puntos (por ejemplo, los sistemas de archivos, bases de datos y aplicaciones empresariales personalizadas) mediante el uso de varios protocolos de comunicación. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona adaptadores nativos compatibles con varios protocolos. Estos incluyen:  
  
- Un adaptador de archivo que admite el envío y la recepción de mensajes desde una ubicación de archivo.  
  
- Adaptadores para protocolos EDI, FTP, HTTP, MSMQ, SMTP, POP3 y SOAP.  
  
- Un adaptador para [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]  
  
  En algunos casos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que necesite transportar mensajes a una aplicación personalizada específica o usar un protocolo para el que no existe un adaptador nativo. Las compañías de terceros han escrito adaptadores compatibles con otros protocolos. Antes de decidirse a escribir un adaptador personalizado, puede que desee saber si ya hay un adaptador para el protocolo. Para obtener una lista de adaptadores y proveedores asociados, consulte [ http://go.microsoft.com/fwlink/?LinkId=47140 ](http://go.microsoft.com/fwlink/?LinkId=47140). Si no consigue encontrar un adaptador compatible para satisfacer los requisitos de comunicación, puede desarrollar un adaptador personalizado propio.  
  
  La escritura de un adaptador personalizado puede resultar todo un desafío. Para simplificar este proceso, Microsoft ha desarrollado una base denominada el marco de trabajo de adaptadores. Puede usar este marco de trabajo como base para el desarrollo junto con el código de origen del adaptador de ejemplo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.  
  
  Los temas de esta sección incluyen sugerencias y recomendaciones para el desarrollo de adaptadores personalizados.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué es el marco de trabajo de adaptadores?](../core/what-is-the-adapter-framework.md)  
  
-   [Cómo crea BizTalk Server una instancia de un adaptador](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [Lotes de mensajes](../core/message-batches.md)  
  
-   [Lotes de mensajes transaccionales](../core/transactional-message-batches.md)  
  
-   [Desarrollo de un adaptador de recepción](../core/developing-a-receive-adapter.md)  
  
-   [Desarrollo de un adaptador de envío](../core/developing-a-send-adapter.md)  
  
-   [Creación de instancias de adaptadores aislados](../core/instantiating-isolated-adapters.md)  
  
-   [Problemas de diseño del adaptador](../core/adapter-design-issues.md)  
  
-   [Cómo controlan los adaptadores mensajes de gran tamaño](../core/how-adapters-handle-large-messages.md)  
  
-   [Cómo controlar errores de adaptador](../core/how-to-handle-adapter-failures.md)  
  
-   [Cómo finalizar un adaptador](../core/how-to-terminate-an-adapter.md)  
  
-   [Cómo diseñar un adaptador de alto rendimiento](../core/how-to-design-a-performant-adapter.md)  
  
-   [Cómo implementar un adaptador personalizado](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [Cómo probar y depurar un adaptador](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [Cómo agregar metadatos de adaptador a un proyecto de BizTalk](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [Problemas de localización de adaptadores](../core/adapter-localization-issues.md)  
  
-   [Sugerencias para diseñar un adaptador](../core/tips-for-designing-your-adapter.md)  
  
-   [Configuración de adaptadores en tiempo de diseño](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de componentes personalizados](../core/developing-custom-components.md)