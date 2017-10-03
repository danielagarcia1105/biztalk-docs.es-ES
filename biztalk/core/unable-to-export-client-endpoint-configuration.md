---
title: "No se puede exportar la configuración de punto de conexión de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941d42ff01bcf578bd7ba7c426c6fe5ca2bfbce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-export-client-endpoint-configuration"></a>No se puede exportar la configuración de extremo de cliente
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede exportar la configuración de extremo de cliente a "{0}".|  
  
## <a name="explanation"></a>Explicación  
 Este error indica una de las situaciones siguientes:  
  
-   El usuario no tiene permiso para escribir en el destino.  
  
     \- O BIEN  
  
-   Algunas de las propiedades necesarias no se especificaron correctamente, como **dirección (URI)** y **BindingType**.  
  
## <a name="user-action"></a>Acción del usuario  
 Utilice el procedimiento siguiente para comprobar los permisos de usuario y confirmar **dirección (URI)** y **BindingType** configuración es válida.  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a>Para comprobar los permisos del usuario y confirmar la configuración  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Localice la aplicación y, a continuación, el transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En WCF **[***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. Asegúrese de que está permitido escribir en la carpeta de destino.  
  
10. Compruebe el **comportamiento** ficha y la **identidad de extremo** configuración de **General** ficha para asegurarse de que son válidos.  
  
> [!NOTE]
>  Debe tener permisos de escritura en la carpeta de destino. Póngase en contacto con el administrador del equipo para obtener estos permisos.