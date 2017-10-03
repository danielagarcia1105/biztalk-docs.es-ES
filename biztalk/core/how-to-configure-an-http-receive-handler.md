---
title: "Cómo configurar controlador de recepción de HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0380804039d45efbe3db06b6fc072a3afb8b6b48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-receive-handler"></a>Cómo configurar controlador de recepción de HTTP
Utilice este procedimiento para configurar las propiedades de un controlador de recepción de HTTP.  
  
> [!NOTE]
>  Cada host sólo podrá tener un controlador de recepción asociado.  
  
> [!NOTE]
>  El adaptador de recepción de HTTP se ejecuta en el contexto de una instancia de host aislado de BizTalk.  
  
> [!CAUTION]
>  Al usar controladores de adaptador de HTTP o de SOAP, se recomienda instalar las instancias de host de estos controladores en equipos de Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a>Para configurar las propiedades generales de un controlador de recepción de HTTP  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **HTTP,** en el panel derecho, haga clic en el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.  
  
4.  Haga clic en **propiedades** para tener acceso a la **tamaño de los lotes** controlador de recepción de propiedad para el HTTP.  
  
5.  Escriba un valor entre 1 y 256 y haga clic en **Aceptar**.  
  
6.  Haga clic en **Aceptar**.  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] está diseñado para procesar lotes de mensajes eficazmente y no para procesar un único mensaje muy rápidamente. Por lo que si se va a usar este controlador de recepción para ubicaciones de recepción bidireccionales o de solicitud-respuesta, puede minimizar la latencia siguiendo estos pasos:  
  
-   Establecer el **tamaño de los lotes** en un valor de 1.  
  
-   Reducir el **MaxReceiveInterval** valor entre el valor predeterminado de 500 y un valor inferior a 100 para la **Messaging Isolated, XLANG/s,** y **Messaging In-Process** servicio clases.  Se realizan cambios el **adm_ServiceClass** tabla de la base de datos de administración de BizTalk, que contiene un registro para cada uno de estos tipos de servicio.  Tenga cuidado al cambiar esta configuración porque se trata de un cambio amplio de tipo de servicio. Esta configuración especifica el intervalo máximo de sondeo (en milisegundos) para que el agente de mensajería de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sondee la base de datos de cuadro de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para ver si hay mensajes.  También se usa por el controlador de limitación para decidir si se necesita la limitación de mensajes bajo determinadas condiciones de carga. Si es necesario, el controlador de limitación retrasará de manera incremental el intervalo de distribución de mensajes según las condiciones de sobrecarga del sistema. En un sistema de alto rendimiento, esa configuración no se usará.  Sin embargo, una vez usados estos valores, el intervalo de tiempo cambiará dinámicamente entre MaxReceiveInteral/10 y MaxReceiveInterval.  
  
    > [!NOTE]
    >  Si cambia esta configuración afecta a todos los hosts que se crean con un **tipo de Host** de **Isolated**.  
  
-   Reinicie los grupos de aplicaciones de IIS asociados con las funciones de recepción HTTP configuradas.  
  
 La cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** instancia de host debe tener de lectura y permisos de escritura en el directorio o directorios temporales para compilar dinámicamente los archivos de código subyacente utilizados HTTP recepción (función). Utilice el procedimiento siguiente para conceder los permisos.  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a>Para conceder a la cuenta de la instancia de host BizTalkServerIsolatedHost los permisos de lectura y escritura en el escritorio temporal de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **CMD**, y presione ENTRAR.  
  
2.  En el símbolo del sistema, escriba **set TEMP** y presione ENTRAR para mostrar el directorio asociado con el **TEMP** variable de entorno.  
  
3.  En el símbolo del sistema, escriba **set TMP** y presione ENTRAR para mostrar el directorio asociado con el **TMP** variable de entorno.  
  
 Conceda a la cuenta que se especifica como la cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** hospedar la instancia de lectura y permisos de escritura en el directorio o directorios asociados con la **TEMP** y  **TMP** variables de entorno. Para determinar la cuenta de inicio de sesión para la **BizTalkServerIsolatedHost** instancia, en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda  **Grupo de BizTalk**, expanda **configuración de plataforma**, expanda **instancias de Host**, haga clic en el **BizTalkServerIsolatedHost** host instancia en el panel derecho y, a continuación, haga clic en **propiedades**. La cuenta de inicio de sesión usada para la instancia de host aparece junto a la **inicio de sesión** etiqueta.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador HTTP](../core/configuring-the-http-adapter.md)