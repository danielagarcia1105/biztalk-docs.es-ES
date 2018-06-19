---
title: Requiere el tipo de enlace de propiedad no se especifica (R2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a34de62453bd252e110edd0caf8a71996f25ae3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268812"
---
# <a name="required-property-binding-type-not-specified-r2"></a>No se ha especificado la propiedad necesaria Tipo de enlace (R2)
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se ha especificado la propiedad necesaria Tipo de enlace.|  
  
## <a name="explanation"></a>Explicación  
 No ha especificado la propiedad Tipo de enlace al configurar un transporte WCF-Custom o WCF-CustomIsolated.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar la propiedad de tipo de enlace.  
  
#### <a name="to-configure-the-binding-type-property"></a>Para configurar la propiedad de tipo de enlace  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF--[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. Especifique un valor en el **BindingType** lista.  
  
 Para obtener más información sobre la configuración de enlaces, vea los recursos siguientes:  
  
-   [Cómo configurar un WCF-CustomIsolated ubicación de recepción](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Cómo configurar un WCF-Custom ubicación de recepción](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [Cómo configurar un puerto de envío WCF-Custom](../core/how-to-configure-a-wcf-custom-send-port.md)