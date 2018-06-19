---
title: Escenarios de alta disponibilidad de servidor BizTalk Server de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- examples, high availability
- architecture, examples
- high availability, examples
- examples, architecture
- databases, clustering
- architecture, medium distributions
- scaling
- architecture, large distributions
ms.assetid: ad9e3f57-1a23-41c2-82c9-dc8e1b29ed4d
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff4db96e89dc91ee96aaf5f0b60f0de34ce83425
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271668"
---
# <a name="sample-biztalk-server-high-availability-scenarios"></a>Escenarios de ejemplo de alta disponibilidad de BizTalk Server
Este tema describe los escenarios de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporcionan alta disponibilidad mediante niveles de hosts escalados horizontalmente. Al separar las áreas de funcionalidad en hosts diferentes y niveles de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], los administradores pueden proporcionar redundancia para cada host y escalarlos de forma independiente de otros hosts. Para proporcionar alta disponibilidad para cada área funcional, cree hosts independientes para cada función principal, recibir, procesar, enviar y seguimiento y clúster el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos y la Enterprise Single Sign-On servidor secreto principal.  
  
## <a name="small-biztalk-server-deployments"></a>Implementaciones de BizTalk Server de tamaño pequeño  
 La implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] más pequeña que proporciona alta disponibilidad para SQL Server y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consta de dos equipos que tienen una configuración de clúster activo/activo para SQL Server. Ambos equipos contienen instancias de todos los hosts de BizTalk del entorno. Si un equipo deja de funcionar o encuentra errores, el otro equipo mantiene la disponibilidad del servicio para SQL Server y para BizTalk Server. Esta configuración no tiene una alta disponibilidad porque no acomoda la agrupación en clúster del servidor secreto maestro, ya que las instancias de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se iniciarán en un equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] donde el recurso de inicio de sesión único empresarial en clúster está pasivo. Para obtener más información acerca de los clústeres del servidor secreto principal, consulte [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).  
  
 Para pequeñas [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las implementaciones que contienen menos de cinco equipos, se recomienda que el clúster de SQL Server que contiene las bases de datos de BizTalk Server se ejecuta en equipos independientes de los equipos de BizTalk Server. Los equipos con BizTalk Server pueden ejecutar todos los hosts de BizTalk (recepción, procesamiento y envío). Para que esta implementación tenga una alta disponibilidad, agrupe el servidor SQL Server y el servidor secreto principal de inicio de sesión único empresarial, y tenga dos servidores BizTalk Server que ejecuten, cada uno, una instancia de los hosts del entorno.  
  
 La siguiente ilustración muestra una implementación pequeña de BizTalk Server que tiene una alta disponibilidad.  
  
 ![Implementación de BizTalk Server](../core/media/tdi-highava-smalldepl.gif "TDI_HighAva_SmallDepl")  
  
## <a name="medium-sized-biztalk-server-deployments"></a>Implementaciones de BizTalk Server de tamaño medio  
 Para implementaciones de tamaño medio que contengan de cinco a diez equipos, se recomienda agrupar el servidor SQL Server que contenga las bases de datos de BizTalk Server y el servidor secreto principal de inicio de sesión único empresarial. Si el escenario tiene un gran número de operaciones de recepción, puede dedicar dos servidores BizTalk Server a ejecutar las instancias de host de recepción para proporcionar una solución de alta disponibilidad. Después, puede tener dos o más equipos que ejecuten las instancias de host de procesamiento y envío. Para que ésta sea una implementación de alta disponibilidad, cree instancias de los hosts de procesamiento y envío en dos servidores BizTalk. De forma similar, si tiene un escenario con un gran número de operaciones de procesamiento, puede dedicar dos servidores BizTalk a ejecutar las instancias del host de procesamiento y los otros dos servidores BizTalk a ejecutar instancias de los hosts de recepción y envío.  
  
 La siguiente ilustración muestra una implementación de BizTalk Server de tamaño medio con dos servidores BizTalk dedicados a operaciones de recepción.  
  
 ![Medio &#45; Tamaño de la implementación de BizTalk Server](../core/media/tdi-highava-meddepl.gif "TDI_HighAva_MedDepl")  
  
 Para obtener más información sobre la alta disponibilidad para Enterprise Single Sign-On, vea [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).  
  
## <a name="large-scale-biztalk-server-deployments"></a>Implementaciones de BizTalk Server a gran escala  
 Para implementaciones de gran tamaño que contengan 10 o más equipos, dedique equipos con BizTalk Server diferentes para las funciones de recepción, procesamiento y envío. Asimismo, si tiene muchos equipos con BizTalk Server en un grupo, puede incluir equipos adicionales con la base de datos de cuadro de mensajes para aumentar el rendimiento. En este caso, agrupe las bases de datos de cuadro de mensajes y el servidor secreto principal para proporcionar alta disponibilidad.  
  
 Esta configuración distribuida muestra la flexibilidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] porque permite evaluar e identificar puntos específicos del error en la implementación y, a continuación, asignar estratégicamente recursos para reducir esos puntos en el sistema. El entorno empresarial dinámico de hoy día demanda esta flexibilidad porque las fluctuaciones de carga de trabajo y los requisitos empresariales pueden cambiar a diario.  
  
 En lugar de gastar dinero adicional en ampliar o adquirir nuevo hardware, utilice los recursos existentes para lograr alta disponibilidad moviendo recursos de los equipos que consumen menos recursos a equipos que sí hacen un gran uso de ellos.  
  
 La siguiente ilustración muestra una a gran escala [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación.  
  
 ![Grandes &#45; Escalar la implementación de BizTalk Server](../core/media/tdi-highava-largedepl.gif "TDI_HighAva_LargeDepl")  
  
 Para obtener más información sobre la alta disponibilidad para Enterprise Single Sign-On, vea [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).  
  
## <a name="providing-high-availability-using-hyper-v-and-failover-clustering"></a>Alta disponibilidad mediante Hyper-V y clúster de conmutación por error  
 La función Hyper-V de Windows® Server 2008 y la característica de clúster de conmutación por error de Windows Server 2008 se pueden combinar para proporcionar alta disponibilidad a un entorno de equipo servidor virtualizado. Los equipos de BizTalk Server y los equipos de SQL Server usados en una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se pueden instalar en un entorno virtualizado de Hyper-V y luego estar disponibles mediante el clúster de conmutación por error. Puesto que la ejecución de un sistema operativo invitado en Hyper-V conlleva un coste de recursos del sistema, recomendamos realizar una prueba de rendimiento exhaustiva antes de implementar una solución como esta en producción. Para obtener más información acerca del uso de Hyper-V y juntos de agrupación en clústeres de conmutación por error para proporcionar alta disponibilidad para las máquinas virtuales, consulte "Hyper-V Step Guide: Hyper-V y clústeres de conmutación" en [http://go.microsoft.com/fwlink/?LinkID=129113](http://go.microsoft.com/fwlink/?LinkID=129113). Para obtener más información acerca de cómo implementar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno virtualizado de Hyper-V, consulte la Guía de Hyper-V de BizTalk Server disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=189706](http://go.microsoft.com/fwlink/?LinkId=189706).  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)   
 [Proporcionar una alta disponibilidad para bases de datos de servidor BizTalk Server](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [Alta disponibilidad para el inicio de sesión único empresarial](../core/high-availability-for-enterprise-single-sign-on.md)