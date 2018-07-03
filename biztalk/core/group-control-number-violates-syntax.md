---
title: Número de control de grupo infringe la sintaxis | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6580441f828f04697c1d3896d37a6fe8c6ce356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008933"
---
# <a name="group-control-number-violates-syntax"></a>El número de control de grupo infringe la sintaxis.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                          X12FaInvalidControlNumberDescription                          |
|  Texto del mensaje   |                          El número de control de grupo infringe la sintaxis.                          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque el número de control de grupo contenido en los campos GS06 y GE02 del intercambio no se ajustaban al tipo de datos o la longitud que se especifica en el esquema de servicio. El esquema de servicio es X12ServiceSchema en BaseArtifacts.dll.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los números de control de grupo contenidos en los campos GS06 y GE02 del intercambio se ajustan al tipo de datos (X12_N0) y la longitud (entre uno y nueve dígitos) que se especifican en el esquema de servicio y, a continuación, reenvíe el intercambio.