---
title: Falta un elemento de datos obligatorio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966493"
---
# <a name="mandatory-data-element-missing"></a>Falta elemento de datos obligatorio.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      X12DeMandatoryDataElementMissingDescription                       |
|  Texto del mensaje   |                             Falta elemento de datos obligatorio.                             |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante, pues el intercambio no contenía elementos de datos que requiere el esquema del mensaje (para el cual minOccurs es mayor que 0).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el intercambio contiene todos los elementos de datos que requiere el esquema del mensaje y vuelva a enviar el mensaje.