---
title: En conflicto las propiedades de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271b9efa9d30d5c315bfd6061bfbf011289ea620
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012085"
---
# <a name="conflicting-binding-properties"></a>Propiedades de enlace conflictivas
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                    |
| Versión del producto |                                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                |
|    Identificador del evento     |                                                                            0                                                                            |
|  Origen del evento   |                                                                            0                                                                            |
|    Componente    |                                                                            0                                                                            |
|  Nombre simbólico  |                                                                            0                                                                            |
|  Texto del mensaje   | En conflicto las propiedades de enlace: MsmqAuthenticationMode ={0} y MsmqProtectionLevel ={1} no es válido. Cambie una de las propiedades para resolver el conflicto. |
  
## <a name="explanation"></a>Explicación  
 La propiedad de nivel de protección de MSMQ de un transporte WCF-NetMsmq se estableció en **sesión** o **EncryptAndSign** para el modo de autenticación de MSMQ.  
  
## <a name="user-action"></a>Acción del usuario  
 Cambie las propiedades de nivel de protección de MSMQ o modo de autenticación de MSMQ para que sea coherente con la propiedad de nivel de protección de MSMQ.  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **propiedades de transporte WCF-NetMsmq** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
9. Compruebe los valores de MSMQ **modo de autenticación** lista y **nivel de protección de MSMQ** lista.  
  
   Para obtener más información, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo configurar un puerto de envío WCF-NetMsmq](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-NetMsmq](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)