---
title: Cómo configurar asignaciones de entrada para un puerto de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b840f4c418c835765345adc01da5c9c18812d3ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985605"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a>Cómo configurar asignaciones de entrada para un puerto de recepción
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar asignaciones de entrada para un puerto de recepción. Las asignaciones de entrada pueden utilizarse para transformar mensajes de entrada de un esquema a otro (por ejemplo, para transformar mensajes recibidos de un socio comercial en un esquema utilizado en su empresa).  
  
 Se utiliza una asignación para aplicar una transformación XSL a un mensaje enviado por el puerto de recepción, sin tener que procesar el mensaje a través de una orquestación. Es posible agregar una asignación de entrada, quitar una asignación o cambiar una ya existente por otra distinta. Puede agregar más de una asignación a un puerto de recepción, aunque cada asignación debe tener un único esquema de origen. Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede configurar asignaciones para un puerto de recepción durante el proceso de desarrollo mediante el procedimiento de este.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a>Para configurar asignaciones de entrada para un puerto de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar una asignación de entrada para un puerto de recepción.  
  
3. Haga clic en **puertos de recepción**, haga clic en el puerto de recepción, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de entrada**.  
  
4. Configure las asignaciones de entrada tal y como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Quitar**|Quitar la asignación seleccionada.|  
   |**Documento de origen**|Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.|  
   |**Mapa**|Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.|  
   |**Documento de destino**|Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar puertos de recepción](../core/managing-receive-ports.md)   
 [Administración de asignaciones](../core/managing-maps.md)