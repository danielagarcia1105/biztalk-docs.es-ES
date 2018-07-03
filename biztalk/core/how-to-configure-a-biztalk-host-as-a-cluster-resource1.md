---
title: Cómo configurar un Host de BizTalk como un clúster de Resource1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, high availability
- clustering, servers
- hosts, multiple
- hosts, high availability
- Windows Server cluster
- databases, clustering
- clustering, fail-overs
- Windows Server cluster, about Windows Server cluster
- installation, planning
- clustering, databases
- clustering, best practices
- clustering, unclustering
- clustering, configuring
- installation, clustering
ms.assetid: bcd656d2-8dd6-49fc-9c42-ef5c884e52c4
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53df974ec3b0fdf93b4e1cd59c9144b5b33af424
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981989"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>Cómo configurar un host de BizTalk como un recurso de clúster
Este tema explica los pasos que se deben seguir para configurar un host de BizTalk como un recurso de clúster. Para realizar los pasos de este tema, debe haber configurado al menos dos servidores BizTalk Server en un grupo de BizTalk Server como miembros de un clúster de Windows Server. Para obtener más información acerca de la configuración de un clúster de Windows Server, vea la Ayuda en pantalla de Windows Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk para agrupar o desagrupar un host en clústeres.  
  
## <a name="considerations-and-known-issues"></a>Consideraciones y problemas conocidos  
  
- Debe configurar un servidor BizTalk Server como un nodo de un clúster de conmutación por error de Windows Server para poder ejecutar una instancia de un host de BizTalk en clúster en el servidor BizTalk Server. Para obtener más información acerca de la configuración de un nodo de clúster en un clúster de servidores, vea la Ayuda en pantalla de Windows Server.  
  
- No se puede producir un error a través de un host de BizTalk agrupado a una instancia de host que tiene la opción **deshabilitar la instancia de host inicie** establecido. Asegúrese de que todas las instancias del host de BizTalk en clúster tienen esta opción deshabilitada. Esta opción se establece en la consola de administración de BizTalk Server en el **propiedades de la instancia de Host** página.  
  
- Al agrupar un host de BizTalk en clústeres, se crea el recurso de clúster correspondiente en el grupo de recursos de clúster especificado. Cuando se crea el recurso de clúster, cada nodo disponible del clúster se agrega como un propietario posible del recurso de clúster. Dado que un recurso de clúster se puede conmutar por error a cualquier nodo de la lista de propietarios posibles, debe agregar una instancia del host a todos los nodos disponibles de un clúster antes de agrupar un host de BizTalk en clústeres. Los intentos de conmutar por error un host de BizTalk a un equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que no contiene ninguna instancia de host serán erróneos.  
  
  > [!NOTE]
  >  Si desea impedir que un host de BizTalk en clúster se ejecute en un nodo de clúster concreto o que conmute por error a un nodo de clúster específico, quite el nodo de la lista de propietarios posibles del recurso en clúster que se crea al agrupar el host de BizTalk en clústeres. Puede modificar la lista de propietarios posibles de un recurso de clúster con la interfaz de Administración de clúster de conmutación por error de Windows Server.  
  
- Cuando agrupe un host de BizTalk, asegúrese de que el grupo de clústeres, aplicación o servicio en clúster al que está agregando el host contiene un recurso Nombre de red y un recurso Dirección IP. Si el grupo de clústeres de destino contiene un recurso Nombre de red y Dirección IP, el recurso Nombre de red se agrega como dependencia al host de BizTalk en clúster. Si estos recursos no están disponibles, el host de BizTalk no funcionará correctamente como recurso en clúster.  
  
- Si quita la configuración de un nodo de clúster o servidor de BizTalk que aparece como un propietario posible de un host de BizTalk en clúster, el recurso de clúster de la instancia de host se desconecta de Windows Cluster. Si necesita quitar la configuración de un equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que figura como un propietario posible de un host de BizTalk en clúster sin desconectar el recurso de clúster de la instancia de host, siga los pasos siguientes:  
  
  - En la interfaz de Administración de clúster de conmutación por error de Windows Server, conmute por error el host en clúster a un equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que no sea el equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuya configuración va a quitar.  
  
  - En la consola de administración de BizTalk Server, seleccione la instancia de host de BizTalk agrupado que se corresponde con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo que va a ser sin configurar.  
  
  - Elimine la instancia de host. Si le aparece un error, elija la opción de eliminar de forma forzada la instancia de host.  
  
  - Quite la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Cuando se configura un host de BizTalk como host agrupado, se crea un recurso de clúster correspondiente en el grupo de recursos de clúster especificado del clúster.  
  
   De forma predeterminada, se configura un recurso de host de BizTalk en clúster con los siguientes valores de reinicio en un clúster de conmutación por error de Windows Server que están disponibles en el **directivas** pestaña de la **propiedades** cuadro de diálogo para el recurso de clúster:  
  
  |Opción|Valor|  
  |------------|-----------|  
  |Si el recurso tiene errores, intente reiniciar en el nodo actual.|**True** <br />El servicio de clúster intentará reiniciar el recurso en caso de que se produzca un error.|  
  |Periodo para reinicios (mm:ss):|**15:00** <br />Especifica el período de tiempo durante el que se cuentan los intentos de reinicio.|  
  |Máximo de reinicios en el período especificado:|**1** <br />Especifica el número máximo de intentos de reinicio permitidos durante el **período para reinicios (mm: ss)** .|  
  |Si no se reinicia correctamente, conmute por error todos los recursos de este servicio o aplicación.|**True** <br />El servicio de clúster intentará reiniciar el recurso mediante una conmutación por error del grupo de recursos completo a otro nodo de clúster.|  
  |Si todos los intentos de reinicio presentan errores, empiece a reiniciar de nuevo tras el período especificado (hh:mm):|**1:00** <br />Especifica un período de espera extendido después de que el servicio de clúster comenzará otra serie de intentos de reinicio.|  
  |Tiempo de espera pendiente (mm:ss):|**3:00** <br />Especifica el período de tiempo que el recurso puede emplear para cambiar los Estados entre en línea y sin conexión antes de que el servicio de clúster pone el recurso en el estado de error.|  
  
   Los valores de reinicio predeterminados indican que el clúster de conmutación por error de Windows Server intentará reiniciar una instancia con errores de una instancia de host de BizTalk en clúster un máximo de 1 vez dentro del intervalo de tiempo de 15 minutos. Puesto que la **si reinicio se realiza correctamente, conmutar por error todos los recursos de este servicio o aplicación** valor se establece en **True**, cualquier intento de reinicio también conmutará el grupo de recursos de clúster a otro clúster nodo. Si no se puede reiniciar una instancia con errores de un host de BizTalk agrupado en el número especificado de intentos durante el período de tiempo especificado, a continuación, el host de BizTalk agrupado asumirá el estado de **Failed** en la administración de clúster de conmutación por error interfaz. Si un host de BizTalk en clúster asume el estado **Failed** , a continuación, se debe iniciar manualmente en la administración de clúster de conmutación por error.  
  
   De forma predeterminada, se configura un recurso de host de BizTalk en clúster con los siguientes valores de reinicio en un clúster de servidores que están disponibles en el **avanzadas** pestaña de la **propiedades** cuadro de diálogo para el clúster recurso:  
  
  |**Opción**|**Value**|  
  |----------------|---------------|  
  |Reiniciar|**True**<br /><br /> El servicio de clúster intentará reiniciar el recurso en caso de que se produzca un error.|  
  |Afectar al grupo|**True**<br /><br /> El servicio de clúster intentará reiniciar el recurso mediante una conmutación por error del grupo de recursos completo a otro nodo de clúster.|  
  |Umbral de reinicio|**3**<br /><br /> Especifica el número máximo de intentos de reinicio permitidos durante el **período de reinicio**. Si supera el número de intentos de reinicio el **umbral de reinicio** durante el **período de reinicio** , a continuación, el recurso de clúster asume el estado **Failed** y el clúster servicio no intenta más reinicios.|  
  |Período de reinicio|**900 segundos**<br /><br /> Especifica el período de tiempo durante el que se cuentan los intentos de reinicio. El **período de reinicio** se inicializa con el primer intento de reinicio. El recuento de intentos de reinicio se restablece en cero si el **umbral de reinicio** no supera el tiempo que dure la **período de reinicio**.|  
  
   Los valores de reinicio predeterminados indican que el clúster de Windows Server intentará reiniciar una instancia con errores de una instancia de host BizTalk agrupado hasta 3 veces dentro del marco temporal de 900 segundos. Puesto que la **afectan al grupo** valor se establece en **True**, cualquier intento de reinicio también conmutará el grupo de recursos de clúster a otro nodo del clúster. Si no se puede reiniciar una instancia con errores de un host de BizTalk agrupado en el número especificado de intentos durante el período de tiempo especificado, el host de BizTalk agrupado asumirá el estado de **Failed** en Administrador de clústeres. Si un host de BizTalk en clúster asume el estado **Failed**, a continuación, se debe iniciarse manualmente en el Administrador de clústeres.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>Para configurar un host de BizTalk como recurso de clúster  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk [\<servername\>:\<administración base de datos\>]**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic para expandir **Hosts**. La lista de hosts aparecerá en la carpeta.  
  
2. Haga clic en el host que le gustaría agrupar en clúster y, a continuación, seleccione **clúster**.  
  
   > [!NOTE]
   >  Asegúrese de que ha creado una instancia de host en todos los nodos de los miembros que sean posibles propietarios de un grupo de clústeres antes de agregar el host de BizTalk a dicho grupo.  
  
3. Seleccione el grupo de clúster que desea que ejecute el host en la lista desplegable de grupos de clúster disponibles.  
  
   > [!NOTE]
   >  Al agrupar un host en clústeres, éste se conecta y comienza el procesamiento de documentos de los controladores de adaptador u orquestaciones que estén configurados para ejecutarse en el host.  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>Para desagrupar un host de BizTalk en clúster  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic para expandir **administración de BizTalk Server**, haga clic para expandir **grupo de BizTalk [\<servername\>:\<administración base de datos\>]**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic para expandir **Hosts**. La lista de hosts aparecerá en la carpeta.  
  
2. Haga clic en el host en clúster que desea quitar del clúster y, a continuación, seleccione **desagrupe**.  
  
   > [!NOTE]
   >  Al desagrupar un host agrupado, cualquier instancia de host asociada con el host agrupado se detendrá y el host detendrá el procesamiento de los documentos de los controladores de adaptador u orquestaciones configurados para ejecutarse en el host.