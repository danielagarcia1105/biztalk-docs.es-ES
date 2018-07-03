---
title: Valor no válido de autorización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674585daa50f0adc0708a792b318bc0b736eca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974437"
---
# <a name="invalid-authorization-value"></a>Valor de autorización no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                       X12Ta1InvalidAuthorizationValueDescription                       |
|  Texto del mensaje   |                              Valor de autorización no válido.                               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el valor de la información sobre autorización en ISA02 no se ajustaba al tipo de datos que especifica el esquema (X12_AN) o no tenía el número de dígitos que requiere el esquema (10). El esquema es X12ServiceSchema en BaseArtifacts.dll.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor del encabezado ISA02 se ajusta al tipo de datos de X12:AN y tiene 10 dígitos (con espacios finales) y vuelva a enviar el intercambio.