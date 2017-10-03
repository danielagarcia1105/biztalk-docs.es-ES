---
title: Crear un entorno de alta disponibilidad BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- architecture, databases
- databases, architecture
- performance
- hosts, multiple
- hosts, architecture
- architecture, hosts
- databases, clustering
- high availability, designing
- BizTalk Server, architecture
- installation, planning
- clustering, databases
- installation, availability
ms.assetid: 758eb3bd-a25b-4863-a4ca-d7a1635f7542
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87044102248d371ea19ed07d676a0e7a0861296e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a>Crear un entorno de BizTalk Server de alta disponibilidad
Esta sección describe cómo proporcionar alta disponibilidad para los datos y las comunicaciones en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuando se integra diversos sistemas y aplicaciones. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]separa los datos de los hosts que procesan los datos, lo que permite resolver problemas ajustando la escala de las bases de datos de disponibilidad y hospeda de forma independiente.  
  
## <a name="demonstrating-high-availability"></a>Demostrar la alta disponibilidad  
 La alta disponibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se centra en la recuperación de componentes funcionales que podrían interrumpir la disponibilidad en una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Para demostrar la alta disponibilidad en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tendrá que aplicar errores y medir la eficacia del producto de recuperación. En las implementaciones de alta disponibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], los errores son trasparentes para las aplicaciones y sistemas externos, y se garantiza que todos los servicios seguirán funcionando correctamente con interrupciones mínimas.  
  
## <a name="designing-for-high-availability"></a>Diseñar alta disponibilidad  
 Diseñar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación que proporciona alta disponibilidad es preciso implementar redundancia para cada componentes funcionales que participan en un escenario aplicación integración de proceso de integración o business. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]simplifica la implementación de estos escenarios separando conceptualmente los datos de los hosts que procesan los datos. Por tanto, para proporcionar alta disponibilidad a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se deben ejecutar varias instancias de host y agrupar en clústeres las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], como se muestra a continuación:  
  
-   **Arquitectura de Hosts de BizTalk** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le permite separar hosts y ejecutar varias instancias de host para proporcionar alta disponibilidad para funciones clave como recibir mensajes, procesar orquestaciones y enviar mensajes. Estos hosts no requieren ningún adicionales de agrupación en clústeres o el mecanismo de equilibrio de carga porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] distribuye automáticamente la carga de trabajo entre varios equipos a través de instancias de host. No obstante, los hosts que ejecutan el controlador de recepción de los adaptadores de HTTP y SOAP requieren un mecanismo de equilibrio de carga como equilibrio de carga de red (NLB) para proporcionar una alta disponibilidad.  
  
-   **Arquitectura de bases de datos de BizTalk Server** alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos normalmente consta de dos o más equipos de base de datos con una configuración de clúster activo/pasivo del servidor de. Estos equipos comparten un recurso de disco común (por ejemplo una matriz de discos SCSI RAID5 o una red de área de almacenamiento) y emplean la Organización por clústeres de Windows para proporcionar redundancia de copia de seguridad y tolerancia a errores.  
  
> [!NOTE]
>  Los entornos de alta disponibilidad son, por naturaleza, entornos de varios equipos. Al configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de varios equipo debe usar cuentas y grupos de usuarios de dominio.  
  
 Puesto que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se basa en Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y Microsoft SQL Server 2008, asegúrese de implementar estos productos con alta disponibilidad antes de configurar los hosts para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los siguientes vínculos incluyen información sobre cómo proporcionar alta disponibilidad a estos productos subyacentes:  
  
-   **High Availability – Always On Technologies**, disponible en [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376).  
  
     Este documento describe las características de alta disponibilidad que están disponibles con SQL Server 2008.  
  
-   **Introducción a soluciones de alta disponibilidad**, disponible en [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377).  
  
     Introduce varias soluciones de alta disponibilidad para SQL Server 2008 que mejoran la disponibilidades de servidores o bases de datos.  
  
-   **Guía paso a paso de servicios de implementación de Windows**, disponible en [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379).  
  
     Contiene una guía detallada de cómo usar el rol de Servicios de implementación de Windows en Windows Server 2008.  
  
-   **Kit de implementación de Windows Server 2003: Planeación de implementaciones de servidor**, disponible en [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433).  
  
     Este libro contiene información sobre cómo planear el almacenamiento en servidores y sobre el diseño y la implementación de servidores de archivos, servidores de impresión y servidores de Terminal Server en organizaciones de mediano y gran tamaño.  
  
-   **Aumentar la disponibilidad de BizTalk Server**, disponible en [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457).  
  
     Sección de la [Guía de operaciones de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=130458) que describe las maneras puede aumentar la disponibilidad de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Proporcionar alta disponibilidad a hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a>Vea también  
 [Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)