---
title: Calificador de autorización no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f893ed867b5783ee1bb9edde49f9f11bf55a7219
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974029"
---
# <a name="invalid-authorization-qualifier"></a>Calificador de autorización no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                     X12Ta1InvalidAuthorizationQualifierDescription                     |
|  Texto del mensaje   |                            Calificador de autorización no válido.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor del calificador de autorización en ISA01 no coincidía con ninguno de los valores de enumeración que especifica el esquema. El esquema es X12ServiceSchema en BaseArtifacts.dll.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor en el encabezado ISA01 coincide con uno de los valores de enumeración especificados por X12ServiceSchema y reenvíe el intercambio.