---
title: 'Lista de comprobación: Proporcionar una alta disponibilidad con equilibrio de carga o de tolerancia a errores | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c93cfc3-05b2-43ad-b0a9-b7f0d2596113
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72976dba4ed30ad6747d2d6175702110fe9730a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299612"
---
# <a name="checklist-providing-high-availability-with-fault-tolerance-or-load-balancing"></a>Lista de comprobación: Proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga
En este tema se enumera los pasos que debe seguir para configurar la tolerancia a errores y equilibrio de carga para los componentes de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno para proporcionar alta disponibilidad. Configuración de tolerancia a errores para estos componentes permitirá que el sistema seguir funcionando si se produce un error en un componente determinado.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Crear varias instancias de host de BizTalk e implementar la compatibilidad con los adaptadores que lo requieran de agrupación en clústeres de host.|[Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|Configurar hosts de seguimiento para lograr alta disponibilidad.|[Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|Configurar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos en un clúster [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia en un clúster de servidores de Windows.|[Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)|  
|Configurar hosts de seguimiento para lograr alta disponibilidad. Compruebe que hay al menos N + 1 las instancias de host con el seguimiento habilitado donde N es el número de bases de datos de cuadro de mensajes en el grupo de BizTalk.|Para habilitar el seguimiento de un host, seleccione la opción de **Permitir seguimiento de Host** en el **propiedades de Host** cuadro de diálogo disponible desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información acerca de cómo establecer las propiedades de host, vea el tema [cómo modificar propiedades de Host](http://go.microsoft.com/fwlink/?LinkId=154359) (http://go.microsoft.com/fwlink/?LinkId=154359).|  
|Practicar la conmutación por error de base de datos con regularidad para garantizar la funcionalidad de conmutación por error.|Esta responsabilidad debe asignarse directamente para asegurarse de que esto se realiza de forma coherente.|  
|Compruebe que hay suficiente capacidad de procesamiento y memoria en los nodos pasivos del clúster para habilitar varios [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias para ejecutarse al mismo tiempo en escenarios de conmutación por error.|Si dos instancias SQL con regularidad consumen más de 50 por ciento de los recursos en nodos de clúster individuales, a continuación, cuando ambas instancias de conmutación por error a un único nodo, cada instancia incurrirá reducción del rendimiento. Por lo tanto, la prueba debe realizarse para garantizar que un solo nodo de clúster será capaz de administrar la carga hasta que el nodo con errores se pone en línea. Si un único nodo no puede controlar la carga de las dos instancias SQL, a continuación, considere la posibilidad de agregar nodos de clúster adicionales para implementar una topología de clúster activo/activo/pasivo.|  
|Implementar una red de área de almacenamiento (SAN) para alojar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. **Nota:** si es posible, configure los discos de SAN mediante RAID topología 1 + 0 (una banda de conjuntos reflejados) para obtener el máximo rendimiento y alta disponibilidad.|En el ["Notas del producto BizTalk Server Database Optimization"](http://go.microsoft.com/fwlink/?linkid=104427) (http://go.microsoft.com/fwlink/?linkid=104427), vea la sección "Infraestructura de disco" en "Performance Tuning".|  
|Usar clústeres de Windows para agrupar el servidor secreto principal de inicio de sesión único (SSO) empresarial.|[Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md) **Nota:** no agrupa el servicio SSO en un equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a menos que el clúster de SSO y un host de BizTalk en el mismo grupo de clúster. Para obtener más información acerca de cómo agrupar el servicio SSO y un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host en el mismo grupo de clúster vea [cómo SSO de clúster y un Host de BizTalk en el mismo grupo de clúster](http://go.microsoft.com/fwlink/?LinkId=154367) (http://go.microsoft.com/fwlink/?LinkId=154367).|  
|Hacer copia de seguridad del secreto principal de inicio de sesión único (SSO) empresarial.|Vea [cómo hacer copia de seguridad del secreto principal](http://go.microsoft.com/fwlink/?LinkID=151395) (http://go.microsoft.com/fwlink/?LinkID=151395).|  
|Configurar el servidor Web de Internet Information Services (IIS) para las instancias de host aislado y la página Web del Portal de BAM para tener alta disponibilidad con equilibrio de carga de red (NLB) o en otra dispositivo de equilibrio de carga.|**Para Windows Server 2008**: vea [Guía de implementación de equilibrio de carga de red](http://go.microsoft.com/fwlink/?LinkId=153139) (http://go.microsoft.com/fwlink/?LinkId=153139).|  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar una alta disponibilidad](../technical-guides/providing-high-availability.md)