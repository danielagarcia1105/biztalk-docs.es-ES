---
title: Un segmento TA1 después de un grupo funcional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87613f9482c5c54e99544b96ddd0d1cfc94d3c85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018142"
---
# <a name="ta1-segment-found-after-a-functional-group"></a>Se ha encontrado un segmento TA1 después de un grupo funcional
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                              TA1FoundAfterFunctionalGroup                              |
|  Texto del mensaje   |     Se ha encontrado un segmento TA1 después de un grupo funcional. Por lo tanto, se rechaza el mensaje.      |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar la confirmación entrante porque ésta contenía un grupo funcional y después un segmento TA1.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente de la confirmación TA1 que se asegure de que el intercambio no contiene un grupo funcional antes del segmento TA1 y vuelva a enviar la confirmación.