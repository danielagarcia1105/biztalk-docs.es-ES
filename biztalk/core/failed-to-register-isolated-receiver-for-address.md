---
title: No se pudo registrar el receptor aislado de dirección | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33aa3e48cd92b3d190289c1d65bf3a3bb7c7907
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986621"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a>No se pudo registrar el receptor aislado de la dirección
## <a name="details"></a>Detalles  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| Versión del producto |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    Identificador del evento     |                                                    0                                                    |
|  Origen del evento   |                                                    0                                                    |
|    Componente    |                                                    0                                                    |
|  Nombre simbólico  |                                                    0                                                    |
|  Texto del mensaje   | No se pudo registrar el receptor aislado de la dirección "{0}"; ubicación de recepción no existe o está deshabilitado. |
  
## <a name="explanation"></a>Explicación  
 Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificado por el atributo receiveLocationName en el archivo Web.config que el Asistente WCF de BizTalk Services publicación genera existe y es se inició.  
  
 Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicación de servicios WCF con los adaptadores de recepción WCF aislados](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-BasicHttp](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar ubicación de recepción de un WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-CustomIsolated](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicación de servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)