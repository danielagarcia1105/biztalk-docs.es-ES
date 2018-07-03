---
title: La entidad de este intercambio AS2 debe contener un valor para AS2-desde | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637224e0519a181c71b12e390c39c821ad354ac6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009253"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a>La entidad de este intercambio AS2 debe contener un valor AS2-From
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                              InvalidAgreementAS2FromName                               |
|  Texto del mensaje   |         La entidad de este intercambio AS2 debe contener un valor AS2-From.          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo enviar el mensaje AS2 porque no se ha configurado la propiedad AS2-From para la entidad resuelta como receptora del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra la consola de administración de BizTalk Server, vaya al nodo Entidades, abra el cuadro de diálogo Propiedades de AS2 de la entidad resuelta para el mensaje, haga clic en el nodo Entidad como receptora del mensaje AS2 y especifique un valor para la propiedad AS2-From.