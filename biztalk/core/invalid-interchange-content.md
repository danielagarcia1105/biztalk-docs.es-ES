---
title: Contenido de intercambio no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2352c3-d233-4d79-be31-b32dde29c8ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc94b838a76b85c248322538328806520ad06723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007629"
---
# <a name="invalid-interchange-content"></a>Contenido de intercambio no válido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                       X12Ta1InvalidInterchangeContentDescription                       |
|  Texto del mensaje   |                              Contenido de intercambio no válido.                               |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque los datos del intercambio no superaron la validación de mensaje que realizó BizTalk Server.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, identifique qué parte del intercambio tuvo un error de validación y qué validación tuvo el error. Resuelva el problema que provocó el error de validación y reenvíe el intercambio.