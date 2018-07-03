---
title: No se puede obtener acceso a la entidad utilizando puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdff3eed53ae042be064bd2e02ff5cecf68c6021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976419"
---
# <a name="unable-to-access-party-using-send-port"></a>No se pudo obtener acceso a la entidad usando el puerto de envío
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                       UnableToLocateAS2PartyBySendPortNameError                        |
|  Texto del mensaje   |                      No se puede obtener acceso a la entidad utilizando puerto de envío: {0}                       |

## <a name="explanation"></a>Explicación  
 Este error indica que la canalización de envío no encontró una entidad asociada con el puerto de envío especificado para el mensaje AS2 saliente.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asocie una entidad con el puerto de envío especificado:  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.  

3. Haga clic con el botón secundario en la entidad correcta.  

4. Haga clic en **Propiedades**.  

5. En el [*nombre de la entidad*] **las propiedades de entidad** cuadro de diálogo, en el panel izquierdo, haga clic en **puertos de envío**.  

6. Escriba el nombre de puerto de envío en el **puertos de envío** lista.  

7. Haga clic en **Aceptar**.
