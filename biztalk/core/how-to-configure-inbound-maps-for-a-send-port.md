---
title: "Cómo configurar asignaciones de entrada para un puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [send ports], inbound maps
- configuring, send ports
- send ports, inbound maps
- configuring, inbound maps
- managing [send ports], configuring
- send ports, configuring
ms.assetid: 213c66ba-928f-4c00-9a87-f45eaa9f7dca
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04179476795e7b7c224b3db1b5e83c8a87f68b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-inbound-maps-for-a-send-port"></a>Cómo configurar asignaciones de entrada para un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de entrada para un puerto de envío. Las asignaciones de entrada se utilizan únicamente con puertos de envío de petición-respuesta estáticos o dinámicos. Se utiliza una asignación para aplicar una transformación XSL a un mensaje de respuesta recibido por el puerto, sin tener que procesar el mensaje a través de una orquestación. Es posible agregar una asignación de entrada, quitar una asignación o cambiar una ya existente por otra distinta. Puede agregar más de una asignación a un puerto de envío, aunque cada una de las asignaciones debe tener un único esquema de origen. Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede configurar asignaciones durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-inbound-maps-for-a-send-port"></a>Para configurar asignaciones de entrada para un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar una asignación de entrada para un puerto de envío.  
  
3.  Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de entrada**.  
  
4.  Configure las asignaciones de entrada tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**. Efectúe las repeticiones necesarias para agregar o quitar varias asignaciones.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Quitar**|Quitar la asignación seleccionada.|  
    |**Documento de origen**|En la lista desplegable, seleccionar el documento origen para la asignación de entrada.|  
    |**Mapa**|En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.|  
    |**Documento de destino**|En la lista desplegable, seleccionar el documento destino para la asignación de entrada.|  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Administración de mapas](../core/managing-maps.md)