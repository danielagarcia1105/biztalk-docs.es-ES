---
title: Administrar el servicio de Bus de eventos BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f265201e371a86072c06b336b4d00bb1742f5f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262820"
---
# <a name="managing-the-bam-event-bus-service"></a>Administrar el servicio de bus de eventos BAM
El servicio de bus de eventos BAM, al que también se conoce como Servicio de descodificación de datos de seguimiento (TDDS), procesa datos de seguimiento (secuencias) almacenados en una base de datos de origen y los conserva de tal forma que resulte fácil solicitarlos posteriormente.  
  
 El servicio de bus de eventos BAM mueve los datos de inteligencia empresarial a la base de datos de importación principal de BAM y los datos de supervisión de estado de BizTalk a la base de datos DTA. El servicio de bus de eventos BAM se ejecuta como un subservicio del servicio de BizTalk.  
  
 Supervisar las actividades de una aplicación transaccional, por ejemplo, Microsoft BizTalk® Server, recopilar datos de eventos durante la ejecución y, a continuación, almacena temporalmente los datos en la misma base de datos como el estado de la aplicación, por ejemplo, la base de datos de cuadro de mensajes.  
  
> [!NOTE]
>  Evite crear más de una instancia de aplicación que aloje el seguimiento para grupos de BizTalk diferentes en el mismo equipo. Si existen instancias que realizan el seguimiento de diferentes grupos de BizTalk en el mismo equipo, no será posible distinguir qué eventos pertenecen a cada grupo de BizTalk en la consola de administración de BizTalk o en el registro de eventos como se muestran todos los grupos de BizTalk con el mismo nombre.  
  
 El servicio de bus de eventos BAM lee los datos de eventos, los descodifica y los almacena en una base de datos de Microsoft SQL Server™ en la que puede consultar los datos fácilmente.  
  
 El servicio de bus de eventos BAM proporciona las ventajas siguientes:  
  
-   Los datos de eventos siempre coinciden con el estado de la aplicación y no muestran nunca un progreso sin confirmar.  
  
-   El impacto del rendimiento en la aplicación que se está ejecutando es mínimo ya que los datos de eventos guardan tan pocos registros en la misma transacción local como el cambio de estado de la aplicación.  
  
-   El almacenamiento del servidor SQL Server para el estado de la aplicación se optimiza aún más para el rendimiento de la ejecución. TDDS descodifica los datos y los almacena en una base de datos independiente, ya sea la base de datos de importación principal de BAM o la base de datos DTA. Cuando se generan informes, los datos se solicitan desde la base de datos, lo que tiene su repercusión en la base de datos de cuadro de mensajes, que es la que almacena el estado de la aplicación.  
  
-   No se realiza el trabajo que almacena los datos de eventos en un formulario que puede consultar en los servidores y bases de datos de aplicaciones. Se descarga en los equipos que ejecutan el servicio de bus de eventos BAM y en la base de datos de destino del servidor SQL Server.  
  
-   Los datos de eventos se procesan con una latencia baja, lo que permite un procesamiento más rápido de las solicitudes de TDDS. Los servicios de bus de eventos BAM coordinan sus recursos para conseguir la latencia mínima posible.  
  
 El servidor de bus de eventos BAM coordina sus recursos al utilizar una conexión a una base de datos central que contiene la información de configuración. Cada servicio de bus de eventos BAM envía un mensaje cada minuto a la base de datos central, que contiene el estado del servicio de bus de eventos BAM en ese momento en particular.  
  
 Este mensaje suele denominarse “mensaje de latido”. Cada servicio de bus de eventos BAM también comprueba si hay trabajos nuevos que se tengan que realizar. Por ejemplo, el servicio de bus de eventos BAM comprueba sesiones que no tienen propietario, como la base de datos de cuadro de mensajes que se ha agregado.  
  
 La sesión de bus de eventos BAM es el movimiento de los datos de eventos de la base de datos de origen, como la de cuadro de mensajes, a la base de datos de destino que contiene los datos de eventos en un formato que puede consultar. El mismo servicio de bus de eventos BAM puede procesar una o más sesiones.  
  
 La ilustración siguiente muestra un grupo de servidores de bus de eventos BAM, que crea un grupo de servidores de bus de eventos BAM.  
  
 ![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")  
Diagrama de un conjunto de servidores de bus de eventos BAM  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Contadores de rendimiento de BAM](../core/bam-performance-counters.md)  
  
-   [Procedimientos almacenados del servicio de Bus de eventos BAM](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [Conmutación por error el servidor de servicio BAM eventos Bus](../core/bam-event-bus-service-server-failover.md)  
  
-   [Creación de instancias del servicio de Bus de eventos BAM](../core/creating-instances-of-the-bam-event-bus-service.md)