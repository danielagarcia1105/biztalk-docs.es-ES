---
title: Cómo configurar opciones de copia de seguridad de transporte para un puerto de envío | Documentos de Microsoft
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
ms.openlocfilehash: 8ff8b1354772290ce9e04742a6130a6f6f2df627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248380"
---
# <a name="how-to-configure-backup-transport-options-for-a-send-port"></a>Cómo configurar opciones de transporte de reserva para un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para configurar las opciones de transporte de reserva para un puerto de envío. El transporte de reserva especificado surte efecto en caso de error del transporte principal. Configuración del transporte primario se describe en [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
> [!NOTE]
>  En el caso de los puertos dinámicos, no hay propiedades disponibles para efectuar la configuración, puesto que las opciones de transporte se determinan de forma automática en tiempo de ejecución.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-specify-transport-options-for-a-send-port"></a>Para especificar opciones de transporte para un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar las opciones de transporte de reserva para un puerto de envío.  
  
3.  Expanda **puertos de envío**, haga clic en el puerto de envío para configurar, haga clic en **propiedades**y, a continuación, haga clic en **copia de seguridad de transporte**.  
  
4.  Configurar las propiedades de transporte de reserva como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipo**|En la lista desplegable, seleccionar el tipo de transporte de reserva, o protocolo de transporte, correspondiente. Si el puerto solo es de petición-respuesta, solo están disponibles en la lista los tipos de transporte que admiten petición-respuesta.|  
    |**Configurar**|Después de seleccionar el tipo de transporte de copia de seguridad, haga clic en **configurar**y, a continuación, configurar propiedades de transporte. Para obtener más información acerca de cómo configurar las propiedades, haga clic en **ayuda**.|  
    |**Controlador de envío**|En la lista desplegable, seleccionar la instancia de host en la que se está ejecutando el adaptador de envío.|  
    |**Número de reintentos**|Especificar el número de veces que el puerto de envío intenta reenviar un mensaje en caso de error. El valor predeterminado es 3; el intervalo permitido es de 0 a 1.000, ambos inclusive.|  
    |**Intervalo de reintento**|Especificar el intervalo de tiempo (en minutos) que media entre los intentos de reenvío de un mensaje. El valor predeterminado es 5; el intervalo permitido es de 0 a 525.600.|  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)