---
title: El esquema de control debería tener segmentos en el orden siguiente ST .... SE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c98bc756e4bd75a8a15111c54f433a7f9c6c0509
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015173"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a>El esquema de control debería tener segmentos en el orden siguiente ST .... SE
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                    SchemaCode116ETransactionSetSchemaStSeOutOfOrder                    |
|  Texto del mensaje   |             El esquema de control debería tener segmentos en el orden siguiente ST .... SE              |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el esquema de documento personalizado no es válido porque los encabezados y finalizadores no estaban en el orden correcto. BizTalk Server realiza esta validación cuando se implementa el esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el esquema del documento personalizado de modo que los encabezados y finalizadores se encuentren en el orden correcto y vuelva a implementar el esquema.