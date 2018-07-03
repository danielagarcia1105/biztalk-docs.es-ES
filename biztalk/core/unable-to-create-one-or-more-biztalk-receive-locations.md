---
title: No se puede crear una o varias ubicaciones de recepción de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b564f87b-34ba-400e-9a71-bd66081fc1b8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dfc81876cba51b4dad03a01c2feb935b4fc959
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986405"
---
# <a name="unable-to-create-one-or-more-biztalk-receive-locations"></a>No se puede crear una o varias ubicaciones de recepción de BizTalk
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |              No se puede crear una o varias ubicaciones de recepción de BizTalk.               |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el Asistente para publicación de Servicio WCF de BizTalk no pudo crear ubicaciones de recepción que hospedan un adaptador de WCF aislado.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que la instancia de BizTalk esté iniciada.  
  
 Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicación de servicios WCF con los adaptadores de recepción WCF aislados](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-BasicHttp](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar ubicación de recepción de un WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-CustomIsolated](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)