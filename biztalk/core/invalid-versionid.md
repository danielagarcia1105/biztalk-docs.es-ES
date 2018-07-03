---
title: Id. de versión no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 563af6e8-f496-46c9-8b5f-7b941b2d08a5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b845c2d7380667ca05bba3567175df04479ae9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976157"
---
# <a name="invalid-versionid"></a>Id. de versión no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                           X12Ta1InvalidVersionIdDescription                            |
|  Texto del mensaje   |                                   Id. de versión no válido.                                    |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el identificador de versión del intercambio (el campo GS08 de un intercambio X12 o el campo UNG7 de un intercambio EDIFACT) no se ajustaba al tipo de datos y al número de dígitos que establece el esquema de servicio (X12ServiceSchema o EdifactServiceSchema en BaseArtifacts.dll). El campo GS08 debe ser del tipo de datos X12_AN y tener entre 1 y 12 dígitos. La versión en UNG7.1 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 3 dígitos. La versión en UNG7.2 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 3 dígitos. El código asignado a la asociación en UNG7.3 debe ser del tipo de datos EDIFACT_AN y tener entre 1 y 6 dígitos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que la versión en GS08 o UNG7 se ajusta al tipo de datos y el número de dígitos que especifica el esquema de servicio y vuelva a enviar el intercambio.