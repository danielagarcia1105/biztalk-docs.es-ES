---
title: Administración de Hosts de BizTalk y las instancias de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1915408853680140643445f4878d9ac925139def
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983405"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a>Administrar hosts de BizTalk e instancias de host
Un host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es un conjunto lógico de cero o más procesos de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se implementan elementos como controladores de adaptador, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones. Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).  
  
 Una instancia de host es el proceso en el que tiene lugar el procesamiento, la recepción y la transmisión de mensajes. Instalar una instancia de host en cada servidor que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que tiene uno o varios hosts asignados a ese servidor. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).  
  
 Los hosts tienen las siguientes características:  
  
- Los hosts son contenedores lógicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Solo puede existir una instancia de un host específico en cada servidor.  
  
- Puede asignar un host a varios servidores.  
  
  Las instancias de host tienen las siguientes características:  
  
- Las instancias de host son contenedores físicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Se crea una instancia de host cuando se asigna un servidor a un host.  
  
- Pueden existir varias instancias de host (o hosts diferentes) en un servidor cuando se efectúa el equilibrio de carga o para la conmutación por error.  
  
  La siguiente ilustración muestra la relación entre servidores, hosts e instancias de host.  
  
  ![Hosts, instancias de host y las relaciones de servidor](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
  Relación entre hosts, instancias de host y servidores  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear un entorno de hospedaje de BizTalk Server](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [Cómo crear un nuevo Host](../core/how-to-create-a-new-host.md)  
  
-   [Cómo modificar las propiedades del Host](../core/how-to-modify-host-properties.md)  
  
-   [Cómo eliminar un Host](../core/how-to-delete-a-host.md)  
  
-   [Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md)  
  
-   [Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)  
  
-   [Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md)  
  
-   [Cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md)  
  
-   [Cómo modificar las propiedades de instancia de Host](../core/how-to-modify-host-instance-properties.md)