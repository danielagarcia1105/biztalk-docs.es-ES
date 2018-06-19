---
title: El intercambio contenía un ISA formado Incorrectamente o el esquema de servicio no estaba disponible | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84aec7600b71d48becfdeb30e34f837292c5ecfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241660"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a>El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|MalformedIsaError|  
|Texto del mensaje|El intercambio contenía un ISA formado incorrectamente o el esquema Servicio no estaba disponible. Se ha rechazado completamente.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque los segmentos ISA o IEA del intercambio no se ajustaban a X12ServiceSchema, o bien X12ServiceSchema (en BaseArtifacts.dll) no estaba implementado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Pida al remitente del intercambio que cambie los segmentos ISA e IEA de modo que se ajusten a X12ServiceSchema.  
  
-   Asegúrese de que BaseArtifacts.dll incluye X12ServiceSchema y está implementado. Para ello, abra la consola de administración de BizTalk Server, el nodo Aplicación EDI de BizTalk y el nodo Esquemas. A continuación, compruebe que X12ServiceSchema aparece en la lista.