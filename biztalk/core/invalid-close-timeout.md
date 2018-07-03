---
title: Tiempo de espera de cierre no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4510329-9fd9-428f-91a3-d72723e9a5e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c7a6a21b57b8e8fbdff75d2c54d00e90b0a55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969477"
---
# <a name="invalid-close-timeout"></a>Tiempo de espera de cierre no válido
## <a name="details"></a>Detalles  

|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  Nombre del producto   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| Versión del producto |                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    Identificador del evento     |                                            0                                             |
|  Origen del evento   |                                            0                                             |
|    Componente    |                                            0                                             |
|  Nombre simbólico  |                                            0                                             |
|  Texto del mensaje   | Tiempo de espera de cierre no válido. Intervalo válido: 0 a 23 horas, 0 a 59 minutos, y 0 a 59 segundos. |

## <a name="explanation"></a>Explicación  

## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el intervalo de tiempo de espera.  

#### <a name="to-configure-the-timeout-range"></a>Para configurar el intervalo de tiempo de espera  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione el puerto correcto.  

7. Haga clic en **configurar**.  

8. En el **WCF [**<em>tipo de transporte</em>**] propiedades** cuadro de diálogo, haga clic en el **enlace** ficha.  

9. Asegúrese de que el intervalo de tiempo de espera sea válido. Los valores aceptados son de 0 a 23 horas, de 0 a 59 minutos y de 0 a 59 segundos.
