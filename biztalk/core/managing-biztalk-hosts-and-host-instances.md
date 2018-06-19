---
title: Administrar instancias de Host y Hosts de BizTalk | Documentos de Microsoft
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
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262588"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a>Administrar hosts de BizTalk e instancias de host
Un host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es un conjunto lógico de cero o más procesos de tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el que se implementan elementos como controladores de adaptador, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones. Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).  
  
 Una instancia de host es el proceso en el que tiene lugar el procesamiento, la recepción y la transmisión de mensajes. Instalar una instancia de host en cada servidor que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que tiene uno o varios hosts asignados a ese servidor. Para obtener más información acerca de las instancias de host, consulte [instancias de Host](../core/host-instances.md).  
  
 Los hosts tienen las siguientes características:  
  
-   Los hosts son contenedores lógicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Solo puede existir una instancia de un host específico en cada servidor.  
  
-   Puede asignar un host a varios servidores.  
  
 Las instancias de host tienen las siguientes características:  
  
-   Las instancias de host son contenedores físicos de objetos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
-   Se crea una instancia de host cuando se asigna un servidor a un host.  
  
-   Pueden existir varias instancias de host (o hosts diferentes) en un servidor cuando se efectúa el equilibrio de carga o para la conmutación por error.  
  
 La siguiente ilustración muestra la relación entre servidores, hosts e instancias de host.  
  
 ![Hosts, instancias de host y las relaciones de servidor](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
Relación entre hosts, instancias de host y servidores  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear un entorno de host de BizTalk Server](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [Cómo crear un nuevo Host](../core/how-to-create-a-new-host.md)  
  
-   [Cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md)  
  
-   [Cómo eliminar un Host](../core/how-to-delete-a-host.md)  
  
-   [Cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md)  
  
-   [Cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)  
  
-   [Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md)  
  
-   [Cómo eliminar una instancia de Host](../core/how-to-delete-a-host-instance.md)  
  
-   [Cómo modificar las propiedades de la instancia de Host](../core/how-to-modify-host-instance-properties.md)