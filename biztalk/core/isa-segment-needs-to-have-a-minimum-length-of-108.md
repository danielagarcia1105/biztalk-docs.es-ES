---
title: El segmento ISA debe tener una longitud mínima de 108 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ecd5c6761c6dbcc59ad6353efa2772b9eecf387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261900"
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a>El segmento ISA debe tener una longitud mínima de 108
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|NseIsaSuffix1LFDescription|  
|Texto del mensaje|El segmento ISA debe tener una longitud mínima de 108. La instancia tiene {0}.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el segmento ISA del intercambio no se ajustaba al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que cada uno de los campos del segmento ISA (desde ISA01 hasta ISA16) tiene el número de dígitos mínimo requerido. Para ver el número mínimo de dígitos, abra la consola de administración de BizTalk Server, así como el nodo Grupo de BizTalk, el nodo Aplicaciones, el nodo Aplicación EDI de BizTalk y, a continuación, el nodo de esquema. Abra Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema con el nodo raíz de ISA y, a continuación, haga clic en la Vista Esquema.