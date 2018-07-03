---
title: Error durante la serialización. El X12 intercambio contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ca3314-6c66-4400-816a-f9c7c7915122
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96c1a186e56fb5c04364187784522f0ba5832581
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008141"
---
# <a name="error-encountered-during-serialization-the-x12-interchange-had-the-following-errors"></a>Error durante la serialización. El intercambio X12 contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| Versión del producto |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    Identificador del evento     |                                                                      -                                                                      |
|  Origen del evento   |                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
|    Componente    |                                                                 Motor EDI                                                                  |
|  Nombre simbólico  |                                                           X12InterchangeSendError                                                           |
|  Texto del mensaje   | Error durante la serialización. El X12 intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI encontró un error al serializar un intercambio X12 saliente debido a los errores indicados con el intercambio identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.