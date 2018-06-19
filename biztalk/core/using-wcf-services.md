---
title: Uso de servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287796"
---
# <a name="using-wcf-services"></a>usar los Servicios WCF
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad integrada para Windows Communication Foundation (WCF). [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]permite reutilizar y agregar todos los servicios WCF existentes en las orquestaciones. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]También incorpora compatibilidad con adaptadores nativos en servicios WCF. La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios WCF sin tener que escribir código. Para obtener información acerca de los adaptadores WCF, vea [adaptadores de WCF](../core/wcf-adapters.md).  
  
 Compatibilidad en los servicios WCF [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se divide en dos categorías: publicación o creación de servicios WCF, o una llamada a o consumir servicios WCF.  
  
 **Publicar servicios WCF**  
  
 Puede publicar (exponer) orquestaciones y esquemas como servicios WCF con los adaptadores de WCF para diferenciar la lógica de servicios WCF de la lógica de procesos empresariales. Para adaptadores aislados de WCF, puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear ubicaciones aisladas de recepción WCF alojadas en aplicaciones Web que se ejecutan en Servicios de Internet Information Server (IIS). Para los adaptadores de WCF de tipo En curso, puede publicar metadatos de servicio para cualquier ubicación WCF con el Asistente para publicación de Servicio WCF de BizTalk.  La publicación de metadatos permite la creación de código de cliente mediante la utilidad svcutil.exe.  
  
 **Consumir servicios WCF**  
  
 Puede usar el Asistente para consumición del Servicio WCF de BizTalk para generar los artefactos de BizTalk, como tipos y orquestaciones de BizTalk, necesarios para consumir un Servicio WCF basado en el documento de metadatos del Servicio WCF. Lo metadatos permiten que un puerto de envío tenga acceso a un servicio externo como cliente. Los metadatos se usan exclusivamente para describir la dirección de extremo, enlace y contrato.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Publicar servicios WCF](../core/publishing-wcf-services.md)  
  
-   [Consumir servicios WCF](../core/consuming-wcf-services.md)  
  
-   [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [Tutoriales del adaptador WCF](../core/wcf-adapter-walkthroughs.md)