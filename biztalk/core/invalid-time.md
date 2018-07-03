---
title: Hora no válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555934e0be188011a69efb3966e5316bc716c254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023826"
---
# <a name="invalid-time"></a>Hora no válida
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                              X12Ta1InvalidTimeDescription                              |
|  Texto del mensaje   |                                      Hora no válida                                      |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque un valor de hora en un elemento de datos no se ajustaba al tipo de datos que especifica el esquema EDI o el valor de hora en el encabezado del campo GS05 en un intercambio X12 no se ajusta al esquema de servicio (X12ServiceSchema in BaseArtifacts.dll). Para X12, el esquema de servicio define una hora en el campo GS05 según el tipo de datos X12_TM y de entre cuatro y ocho caracteres de longitud.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que un valor de hora en un elemento de datos se ajusta al tipo de datos que especifica el esquema EDI o un valor de hora en el encabezado GS05 de un intercambio X12 se ajusta al esquema de servicio y vuelva a enviar el intercambio.