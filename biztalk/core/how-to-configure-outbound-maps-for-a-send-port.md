---
title: Cómo configurar asignaciones de salida para un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1dc02d2936cad6fd24ee944e3c27c64831bc65f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023186"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a>Cómo configurar asignaciones de salida para un puerto de envío
En este tema se describe cómo configurar asignaciones de salida para un puerto de envío mediante la consola de administración de BizTalk Server. Se utiliza una asignación para aplicar una transformación XSL a un mensaje enviado por el puerto de envío, sin tener que procesar el mensaje a través de una orquestación. Es posible agregar una asignación de salida, quitar una asignación o cambiar una ya existente por otra distinta. Puede agregar más de una asignación a un puerto de envío, aunque cada una de las asignaciones debe tener un único esquema de origen. Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a>Para configurar asignaciones de salida para un puerto de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee configurar las asignaciones de salida para un puerto de envío.  
  
3. Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **asignaciones de salida**.  
  
4. Configurar asignaciones de salida como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**. Efectúe las repeticiones necesarias para agregar o quitar varias asignaciones.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Quitar**|Quitar la asignación seleccionada.|  
   |**Asignaciones de salida - documento de origen**|En la lista desplegable, seleccionar el documento origen para la asignación de salida.|  
   |**Asignaciones de salida - asignación**|En la lista desplegable, seleccionar la asignación para asociarla con los documentos de origen y de destino.|  
   |**Asignaciones de salida - documento destino**|En la lista desplegable, seleccionar el documento destino para la asignación de salida.|  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)   
 [Administración de asignaciones](../core/managing-maps.md)