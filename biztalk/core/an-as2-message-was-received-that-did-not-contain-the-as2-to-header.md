---
title: Se recibió un mensaje AS2 que no contenía AS2-al encabezado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343a9b41-fcd9-4508-ac65-9b6e05ec6496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7176966bb22a38ba32ae5203f5ac142bdfd9df4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230140"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a>Se recibió un mensaje AS2 sin el encabezado AS2-To.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|-|  
|Texto del mensaje|Se recibió un mensaje AS2 sin el encabezado AS2-To.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el mensaje AS2 entrante porque el mensaje no contiene un encabezado AS2-To que indique su origen. Los mensajes AS2 deben tener un encabezado AS2-To. El mensaje se suspenderá si no tiene un encabezado AS2-To.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Asegúrese de que la entidad remitente agrega un encabezado AS2-To al encabezado HTTP, AS2 y MIME del mensaje AS2 antes de enviarlo.