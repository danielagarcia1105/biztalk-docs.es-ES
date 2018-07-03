---
title: Crear error en el comando ubicaciones de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f73ff211-af7f-40be-ad7e-7bde7bf75a2d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95b50fcb051b77b4d6516145a2c7fabfc52c2e7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976253"
---
# <a name="create-receive-locations-command-failed"></a>Error en el comando de creación de ubicaciones de recepción
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |  Crear error en el comando ubicaciones de recepción: FileName ={0} argumentos ={1} ExitCode ={2}  |
  
## <a name="explanation"></a>Explicación  
 El Asistente para publicación no pudo crear una ubicación de recepción.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.  
  
 Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicación de servicios WCF con los adaptadores de recepción WCF aislados](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-BasicHttp](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar ubicación de recepción de un WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-CustomIsolated](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)