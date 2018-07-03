---
title: La comparación solo puede ser Equals, NotEquals y Exists | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50499ea6ab9f002d36c213a8bca871884d3b077a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023474"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a>La comparación solo puede tener los valores Igual a, No es igual a y Existe
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                 Err_InvalidComparision                                 |
|  Texto del mensaje   |                La comparación solo puede tener los valores Igual a, No es igual a y Existe.                |
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que BizTalk Server no ha podido comparar una propiedad de contexto mientras intenta decidir si procesar un mensaje por lotes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el filtro proporcionado en los lotes activos no especifica un operador distinto de igual, los valores y existe para tipos XSD que no son compatibles con otras operaciones.