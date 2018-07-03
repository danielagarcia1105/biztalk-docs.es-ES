---
title: Se recibió un mensaje AS2 que no contenía el AS2-de encabezado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 899f9b21-b321-49a3-84bd-a5410c883968
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8471dfe16338f71785062eca4484ca53185931d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005269"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-from-header"></a>Se recibió un mensaje AS2 que no contenía el AS2-de encabezado
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |          Se recibió un mensaje AS2 que no contenía el AS2-de encabezado          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo procesar el mensaje AS2 entrante porque el mensaje no contiene un encabezado AS2-From que indique su origen. Los mensajes AS2 deben tener un encabezado AS2-From. El mensaje se suspenderá si no tiene un encabezado AS2-From.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Asegúrese de que la entidad remitente agrega un encabezado AS2-To al encabezado HTTP, AS2 y MIME del mensaje AS2 antes de enviarlo.