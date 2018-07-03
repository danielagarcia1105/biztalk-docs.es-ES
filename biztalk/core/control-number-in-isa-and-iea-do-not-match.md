---
title: Número de control de ISA e IEA no coinciden con | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fa574e63444740e85cbdd9bf8ac411c495b24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016232"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a>El número de control de ISA e IEA no coinciden.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                       El número de control de ISA e IEA no coinciden.                       |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 no pudo procesar el intercambio entrante porque los números de control del intercambio contenidos en los campos ISA13 e IEA02 del intercambio no tienen el mismo valor.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que los números de control de intercambio contenido en los campos ISA13 e IEA02 del intercambio tienen el mismo valor y, a continuación, reenvíe el intercambio.