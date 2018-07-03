---
title: Error durante la serialización. El intercambio Edifact contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb97be1be3c623673d2429a20598c748a8d73de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000829"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a>Error durante la serialización. El intercambio Edifact contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| Versión del producto |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    Identificador del evento     |                                                                        -                                                                         |
|  Origen del evento   |                              EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
|    Componente    |                                                                    Motor EDI                                                                    |
|  Nombre simbólico  |                                                            EfactInterchangeSendError                                                             |
|  Texto del mensaje   | Error durante la serialización. El intercambio Edifact con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío EDI encontró un error al serializar un intercambio EDIFACT saliente debido a los errores indicados con el intercambio identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.