---
title: Error estructural detectado durante la serialización de un mensaje XML de intercambio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e5ce0694b60afcb743c138d3059a78f63f6fcb5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994301"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a>Error estructural detectado durante la serialización de un mensaje XML de intercambio
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                  InvalidXmlNodeFound                                   |
|  Texto del mensaje   |    Error estructural detectado durante la serialización de un mensaje Xml de intercambio.     |

## <a name="explanation"></a>Explicación  
 Este error indica que se encontró un error estructural durante la serialización de un mensaje XML de intercambio. BTS buscaba un StartElement o EndElement XML, pero encontró un tipo de nodo XML diferente.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que la estructura del mensaje es correcta y vuelva a intentarlo:  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]y haga clic en **grupo de BizTalk**.  

3. En el panel derecho, haga clic en el **concentrador de grupo** ficha.  

4. Haga clic en **instancias de servicio suspendidas**.  

5. Haga doble clic en el mensaje.  

6. En el **detalles del servicio** ventana, haga clic en el **mensajes** ficha.  

7. Haga doble clic de nuevo en el mensaje.  

8. En el panel izquierdo, haga clic en **partes de mensaje / cuerpo**.  

9. Determine si la estructura del mensaje es correcta.
