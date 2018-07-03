---
title: No se puede crear el enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 567b3d88ced85f427fde492cd3e68cefaaf47394
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999207"
---
# <a name="cannot-create-binding"></a>No se puede crear el enlace
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| Versión del producto |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    Identificador del evento     |                                                                       0                                                                        |
|  Origen del evento   |                                                                       0                                                                        |
|    Componente    |                                                                       0                                                                        |
|  Nombre simbólico  |                                                                       0                                                                        |
|  Texto del mensaje   | No se puede crear el enlace; no se especificó el tipo de enlace. Especifique un tipo de enlace como "basicHttpBinding", "wsHttpBinding" o "customBinding. |
  
## <a name="explanation"></a>Explicación  
 No estableció la propiedad BindingType en el código después de configurar un transporte WCF-Custom o WCF-CustomIsolated. O bien el problema podría estar en otras rutas de código. Debe haber un valor en la interfaz de usuario para la opción de enlace. Revise la configuración y asegúrese de que se haya elegido un tipo de enlace de la lista desplegable del área Propiedades de la ubicación de recepción.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, revise el código que configura el transporte WCF-Custom o WCF-CustomIsolated. Asegúrese de que el **BindingType** propiedad de los datos XML para el **TransportTypeData** propiedad de la interfaz ITransportInfo está configurada correctamente.  
  
 Además, especifique un tipo de enlace como **basicHttpBinding**, **wsHttpBinding**, o **customBinding**.  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. Asegúrese de que se especifica un valor en el **BindingType** lista.  
  
   Para obtener más información sobre la configuración de enlaces, vea los recursos siguientes en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo configurar ubicación de recepción de un WCF-CustomIsolated](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Cómo configurar ubicación de recepción de un WCF-Custom](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [Cómo configurar un puerto de envío WCF-Custom](../core/how-to-configure-a-wcf-custom-send-port.md)