---
title: El valor de propiedad unsigned integer no es válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63b0398f-7848-4971-8c08-95923d80cbe3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6af46fc5719e8ccbe52dbfb419e104915d051e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973941"
---
# <a name="the-unsigned-integer-property-value-is-not-valid"></a>El valor de propiedad unsigned integer no es válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                               Err_InvalidUnsignedInteger                               |
|  Texto del mensaje   |                   El valor de propiedad unsigned integer no es válido.                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes o no.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica una propiedad de contexto que tenga el tipo XSD unsigned integer con un valor no válido.