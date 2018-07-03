---
title: No se puede exportar la configuración de punto de conexión de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2418517b7695aedd5c80a950a9b74faf5d380346
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973357"
---
# <a name="unable-to-export-service-endpoint-configuration"></a>No se puede exportar la configuración de extremo de servicio
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |              No se puede exportar la configuración de punto de conexión de servicio para "{0}"              |
  
## <a name="explanation"></a>Explicación  
 Este error indica que es posible que el usuario no disponga de permiso de escritura en el destino. O bien, alguna de las propiedades necesarias no se especificó correctamente, tal como Dirección (URI) y Tipo de enlace.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar la identidad de extremo.  
  
#### <a name="to-configure-the-endpoint-identity"></a>Para configurar la identidad de extremo  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3. Busque la aplicación y, a continuación, busque su transporte.  
  
4. Haga clic con el botón secundario en el nombre del transporte.  
  
5. Haga clic en **Propiedades**.  
  
6. En el puerto **tipo** lista, seleccione el puerto correcto.  
  
7. Haga clic en **configurar**.  
  
8. En WCF **[**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **enlace** ficha.  
  
9. Asegúrese de que se permite la escritura en la carpeta de destino.  
  
10. Compruebe el **comportamiento** ficha y el **identidad de extremo** configuración en el **General** ficha para asegurarse de que son válidos.  
  
    > [!NOTE]
    >  Debe tener permisos de escritura en la carpeta de destino. Póngase en contacto con el administrador del equipo para obtener estos permisos.