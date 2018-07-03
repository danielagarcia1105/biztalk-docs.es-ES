---
title: El intercambio EDIFACT debía contener UNA o UNB como primer segmento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ee9d5100c8378b5ee411673c4c185dcf5def365
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017838"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>El intercambio Edifact debía contener UNA o UNB como primer segmento
## <a name="details"></a>Detalles  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  Nombre del producto   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| Versión del producto |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    Identificador del evento     |                                                -                                                 |
|  Origen del evento   |      EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
|    Componente    |                                            Motor EDI                                            |
|  Nombre simbólico  |                                                -                                                 |
|  Texto del mensaje   | El intercambio Edifact debía contener UNA o UNB como primer segmento. En su lugar {0} encontró |
  
## <a name="explanation"></a>Explicación  
 Este evento de Error, advertencia o información indica que la recepción de EDI canalización no pudo procesar el intercambio EDIFACT entrante debido a que el primer segmento era ni UNA ni un segmento UNB. El segmento UNA es opcional; el segmento UNB, obligatorio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el remitente del intercambio incluye un segmento UNA o UNB como primer segmento del intercambio y vuelva a enviar el intercambio.