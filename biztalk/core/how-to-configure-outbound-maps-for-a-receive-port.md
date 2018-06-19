---
title: Cómo configurar asignaciones de salida para un puerto de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248516"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a>Cómo configurar asignaciones de salida para un puerto de recepción
En este tema, se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de salida para un puerto de recepción. Las asignaciones de salida pueden utilizarse con puertos de recepción de solicitud-respuesta para transformar mensajes de salida de un esquema a otro (por ejemplo, para transformar mensajes que utiliza la empresa en un esquema que utiliza un socio comercial).  
  
 Se utiliza una asignación para aplicar una transformación XSL a un mensaje de respuesta enviado por el puerto de recepción, sin tener que procesar el mensaje a través de una orquestación. Es posible agregar una asignación de salida, quitar una asignación o cambiar una ya existente por otra distinta. Puede agregar más de una asignación a un puerto de recepción, aunque cada asignación debe tener un único esquema de origen. Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a>Para configurar asignaciones de salida para un puerto de recepción  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee configurar asignaciones de salida para un puerto de recepción.  
  
3.  Expanda **puertos de recepción**, haga clic en el puerto de recepción, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de salida**.  
  
4.  Configurar las asignaciones de salida tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Quitar**|Quitar la asignación seleccionada.|  
    |**Documento de origen**|Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.|  
    |**Mapa**|Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.|  
    |**Documento de destino**|Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)   
 [Administración de mapas](../core/managing-maps.md)