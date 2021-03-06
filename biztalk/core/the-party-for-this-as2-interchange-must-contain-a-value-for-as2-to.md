---
title: La entidad de este intercambio AS2 debe contener un valor para AS2-para | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333657b16b0e4a0b9bbbb30c73641f7db8466b87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006701"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a>La entidad de este intercambio AS2 debe contener un valor para AS2-To
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                               InvalidAgreementAS2ToName                                |
|  Texto del mensaje   |          La entidad de este intercambio AS2 debe contener un valor para AS2-To.           |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de envío no pudo procesar el mensaje AS2 saliente porque no se ha configurado la propiedad AS2-To para la entidad resuelta como receptora del mensaje. Esto indica que la entidad para el mensaje AS2 saliente se ha resuelto al hacer coincidir el puerto de envío asociado con la entidad con el puerto de envío que suscribió el mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente:  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Vaya al nodo Entidades y abra el cuadro de diálogo Propiedades de AS2 para la entidad resuelta para el mensaje.  
  
3.  Haga clic en el nodo Entidad como receptora del mensaje AS2  
  
4.  Escriba un valor para la propiedad AS2-To.