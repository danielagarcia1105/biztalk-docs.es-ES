---
title: Solución de administración de procesos de componentes de la empresa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, back-end systems, process management solutions
- process management solution tutorial, client applications
- orchestrations, process management solutions
- adapters, process management solutions
- process management solution tutorial, adapters
- client applications, process management solutions
- process management solution tutorial, components
- process management solution tutorial, orchestrations
- pipelines, process management solutions
- process management solution tutorial, pipelines
- assemblies, process management solutions
- process management solution tutorial, assemblies
ms.assetid: e3ccebb9-b677-4c17-acd2-0f986f7bd3f0
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b63234dbf4a8dc62a620bf2b384b832e4887b0d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234148"
---
# <a name="components-of-the-business-process-management-solution"></a>Componentes de la solución de administración de procesos empresariales
En esta sección se describen los principales componentes de BizTalk Server de la solución Administración de procesos empresariales. Para obtener información acerca de los archivos de origen, consulte [inventario de archivos para la solución de administración de procesos empresariales](../core/file-inventory-for-the-business-process-management-solution.md).  
  
## <a name="orchestrations"></a>Orquestaciones  
 Hay dos orquestaciones principales: **OrderBroker** y **OrderManager**. El **OrderBroker** orquestación acepta solicitudes de cliente a través de un servicio Web o en lotes a través de FTP y envía respuestas a través de una cola de Microsoft Message Queuing (MSMQ). Las solicitudes van desde el **OrderBroker** a la **OrderManager**. Las dos orquestaciones están enlazadas directamente a través de la base de datos de cuadro de mensaje.  
  
 El **OrderManager** ejecuta las solicitudes a través de dos fases de procesamiento asincrónico mediante el **CableOrder1** y **CableOrder2** orquestaciones. Tomadas juntas, las **CableOrder1** y **CableOrder2** orquestaciones representan un único proceso empresarial. Sin embargo, el proceso se divide en dos orquestaciones para que las fases puedan cambiarse sin que se altere el procesamiento del pedido. Para obtener más información sobre el diseño de las fases, vea "Dividir procesos empresariales" en [algunos principios de diseño de la solución de administración de procesos empresariales](../core/some-design-principles-in-the-business-process-management-solution.md).  
  
 El **CableOrder1** orquestación utiliza la **validar** orquestación para validar el pedido y traducir los códigos de solicitud en acciones y llama a la orquestación analizar para analizar el pedido y, a continuación, se llama el **activar**, **cancelar**, o **cambio** orquestaciones, según la acción necesaria. El **CableOrder2** controla la finalización del pedido mediante una llamada a la **completar** orquestación. Tenga en cuenta que **CableOrder1** y **CableOrder2** usar **llamar** formas para invocar las orquestaciones subordinadas.  
  
> [!NOTE]
>  El **cancelar** orquestación incluye un bloque de compensación que llama el **activar** orquestación. De esta forma se garantiza que el pedido se restaura correctamente como parte de la compensación en la solicitud de cancelación.  
  
 El **CableOrder1** y **CableOrder2** las orquestaciones utilizan el enlace directo. Para obtener más información sobre el enlace directo de estas orquestaciones, consulte [pone de manifiesto de implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md).  
  
 Muchas de las orquestaciones se escriben para que puedan interrumpirse durante el procesamiento mediante la **interrupción** orquestación. Para obtener más información sobre el mecanismo de interrupción, consulte [lógica del Administrador de procesos](../core/process-manager-logic.md).  
  
## <a name="back-end-applications"></a>Aplicaciones de servidor  
 La solución Administración de procesos empresariales emplea simulaciones en todas las aplicaciones de servidor. **CableOrder1**, **CableOrder2**, y las orquestaciones que usan todos emplean una clase especial **OrderHandler** objeto. El **OrderHandler** utiliza .NET remoting para comunicarse con una simulación de un sistema de administración de pedidos. El **CableProvisioningSystemClient** y **BTSScnBPMProvisioning** (la **CableProvisioningSystemServer** proyecto) ensamblados simulan los extremos frontales y trasero de el orden en que administra el sistema, respectivamente.  
  
 La solución utiliza una aplicación de Windows forms, **BSTScnBPMFacilities** (la **simulador de instalaciones** proyecto), para simular el servidor MSMQ que controla las solicitudes de servicios.  
  
 Además de estos componentes, las orquestaciones también realizan entradas en una base de datos de SQL Server a fin de conservar un historial de los pedidos y su procesamiento.  
  
## <a name="pipelines"></a>Canalizaciones  
 La solución emplea únicamente canalizaciones predeterminadas estándar que estén configuradas a través de la consola de administración de BizTalk o archivos de enlace. No obstante, las canalizaciones utilizan en numerosas ocasiones la configuración por instancia. El puerto de recepción de pedidos enviado por FTP utiliza la configuración por instancia para definir el sobre. Para obtener más información acerca de la configuración por instancia, consulte [cómo implementar canalizaciones](../core/how-to-deploy-pipelines.md).  
  
## <a name="custom-adapter"></a>Adaptador personalizado  
 La solución utiliza un adaptador personalizado, el **OpsAdapter**, para procesar algunos errores detectados en el **OrderManager** y **ErrorHandler** orquestaciones. Además, emplea el adaptador en los puertos en lo que se especifica el informe de errores. El adaptador obtiene los errores y los envía a los sistemas de operaciones. Para obtener más información acerca de los informes de error, consulte [enrutamiento de mensajes de error utilizando](../core/using-failed-message-routing.md).  
  
## <a name="client-application"></a>Aplicación de cliente  
 La solución incluye una página Web ASP.NET respaldada por un programa de C#, **CSRMain.aspx**, para simular el sistema de servicio al cliente.  
  
## <a name="other-assemblies"></a>Otros ensamblados  
 La solución utiliza otros dos ensamblados, **esquemas** y **utilidades**. El **esquemas** ensamblado define los mensajes de la solución que se utiliza para la comunicación entre las distintas orquestaciones, como el **interrupción** mensaje. La solución también utiliza varios mensajes de .NET definidos en el **SchemaClasses** ensamblado.  
  
 El **utilidades** ensamblado incluye las clases de utilidad y métodos para ayudar a controlar los mensajes, para definir un tipo de excepción específica a la solución, leer valores de configuración desde el almacén secreto de SSO y para ayudar a con control de errores. El ensamblado también incluye el **Recaller** objeto.  
  
 Otros ensamblados incluyen ensamblados de asignaciones y esquemas como **OrderBrokerMaps**, **OrderBrokerSchemas**, **mapas**, **MessagingSchemas**, y **SchemaClasses**.  
  
 El **ServiceLevelTracking** ensamblado contiene los artefactos que se utilizan con BAM para realizar el seguimiento de pedidos y procesamiento. Las acciones de procesamiento de orden utilizadas por las fases se encuentran en el **CableOrderActions** ensamblado.  
  
## <a name="see-also"></a>Vea también  
 [Patrones de la solución de administración de procesos empresariales](../core/patterns-in-the-business-process-management-solution.md)   
 [Procesamiento en la solución de administración de procesos empresariales](../core/processing-in-the-business-process-management-solution.md)   
 [Aspectos destacados de la implementación de la solución de administración de procesos empresariales](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [Supervisión de la solución de administración de procesos empresariales con BAM](../core/monitoring-the-business-process-management-solution-with-bam.md)   
 [Control de versiones de la solución de administración de procesos empresariales](../core/versioning-the-business-process-management-solution.md)   
 [Referencia de solución de administración de proceso empresarial](../core/business-process-management-solution-reference.md)   
 [Desarrollar una solución de administración de procesos empresariales](../core/developing-a-business-process-management-solution.md)   
 [Inventario de archivos para la solución de administración de procesos empresariales](../core/file-inventory-for-the-business-process-management-solution.md)