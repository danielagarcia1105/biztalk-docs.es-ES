---
title: Cómo configurar las opciones de copia de seguridad de transporte para un puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- managing [send ports], configuring
- configuring, backing up [send ports]
- managing [send ports], backup options
- send ports, configuring
- send ports, backup options
ms.assetid: f05f57a6-e62b-4640-a6e2-cb73e9de2a14
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73074cd4b644a3d57765a389ca4120f5b1d799b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979725"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>Cómo configurar opciones de transporte de reserva para un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar las opciones de transporte de reserva para un puerto de envío. El transporte de reserva especificado surte efecto en caso de error del transporte principal. Configuración del transporte primario se describe en [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
> [!NOTE]
>  En el caso de los puertos dinámicos, no hay propiedades disponibles para efectuar la configuración, puesto que las opciones de transporte se determinan de forma automática en tiempo de ejecución.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>Para especificar opciones de transporte para un puerto de envío  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar las opciones de transporte de reserva para un puerto de envío.  
  
3. Expanda **puertos de envío**, haga clic en configurar, haga clic en el puerto de envío **propiedades**y, a continuación, haga clic en **copia de seguridad de transporte**.  
  
4. Configurar propiedades de transporte de copia de seguridad, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Tipo**|En la lista desplegable, seleccionar el tipo de transporte de reserva, o protocolo de transporte, correspondiente. Si el puerto solo es de petición-respuesta, solo están disponibles en la lista los tipos de transporte que admiten petición-respuesta.|  
   |**Configurar**|Después de seleccionar el tipo de transporte de copia de seguridad, haga clic en **configurar**y, a continuación, configurar propiedades de transporte. Para obtener más información acerca de cómo configurar las propiedades, haga clic en **ayuda**.|  
   |**Controlador de envío**|En la lista desplegable, seleccionar la instancia de host en la que se está ejecutando el adaptador de envío.|  
   |**Número de reintentos**|Especificar el número de veces que el puerto de envío intenta reenviar un mensaje en caso de error. El valor predeterminado es 3; el intervalo permitido es de 0 a 1.000, ambos inclusive.|  
   |**Intervalo de reintento**|Especificar el intervalo de tiempo (en minutos) que media entre los intentos de reenvío de un mensaje. El valor predeterminado es 5; el intervalo permitido es de 0 a 525.600, ambos inclusive.|  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)