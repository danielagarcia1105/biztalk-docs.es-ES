---
title: Error durante la serialización. El X12 grupo funcional contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b972993026822aa66b2863a3409e35f0a1b3f434
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009621"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a>Error durante la serialización. El grupo funcional X12 contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| Versión del producto |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    Identificador del evento     |                                                                                        -                                                                                        |
|  Origen del evento   |                                             EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                              |
|    Componente    |                                                                                   Motor EDI                                                                                    |
|  Nombre simbólico  |                                                                           X12FunctionalGroupSendError                                                                           |
|  Texto del mensaje   | Error durante la serialización. El X12 grupo funcional con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el grupo funcional identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el grupo funcional y, a continuación, determine la resolución del problema en la ayuda del producto.