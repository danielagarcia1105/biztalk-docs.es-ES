---
title: "No se puede crear el elemento de configuración de comportamiento de punto de conexión de configuración XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89d906a4-ea85-42d8-8e9e-0a3a7774bcd8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc10a737f2c0a2f344a106868c910a2ecb8144bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a>No se puede crear el elemento de configuración de comportamiento del extremo a partir de la configuración XML.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede crear el elemento de configuración de comportamiento del extremo a partir de la configuración XML.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el adaptador no cargó la configuración de comportamiento del extremo. Esta situación se produce principalmente con los adaptadores de WCF-Custom y WCF-CustomIsolated.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar el comportamiento del extremo.  
  
#### <a name="to-configure-the-endpoint-behavior"></a>Para configurar el comportamiento del extremo  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.  
  
9. En el **comportamiento** sección, compruebe el **EndpointBehavior** configuración.