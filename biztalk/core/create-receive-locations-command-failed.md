---
title: Crear error del comando de ubicaciones de recepción | Documentos de Microsoft
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
ms.openlocfilehash: 2a6ad1c7992bb696eb05223e9830a7114d8a0fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238036"
---
# <a name="create-receive-locations-command-failed"></a>Error en el comando de creación de ubicaciones de recepción
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Crear error del comando de ubicaciones de recepción: FileName = {0} argumentos = \ {1\\} ExitCode = \ {2\}|  
  
## <a name="explanation"></a>Explicación  
 El Asistente para publicación no pudo crear una ubicación de recepción.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.  
  
 Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicar servicios WCF con WCF aislado adaptadores de recepción](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar un WCF-BasicHttp ubicación de recepción](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar un WCF-WSHttp ubicación de recepción](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar un WCF-CustomIsolated ubicación de recepción](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)