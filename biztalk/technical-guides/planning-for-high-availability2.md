---
title: Planeación de alta disponibilidad2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5ff05391eed424e7b910296cc5aa801f8cab1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008333"
---
# <a name="planning-for-high-availability"></a>Planear la alta disponibilidad
Alta disponibilidad para el servidor BizTalk Server se centra en la recuperación de componentes funcionales que podrían interrumpir la disponibilidad en una implementación de BizTalk Server.  
  
 Para demostrar la alta disponibilidad en el servidor BizTalk Server, tendrá que provocan un error y medir la eficacia del producto de recuperación. Una implementación de BizTalk Server de alta disponibilidad, los errores es transparentes para los sistemas y aplicaciones externas y garantiza que todos los servicios seguirán funcionando correctamente con interrupciones mínimas.  
  
 Diseñar una implementación de BizTalk Server que proporciona alta disponibilidad, es preciso implementar redundancia para cada componentes funcionales que participan en una integración de aplicaciones o un escenario de integración de proceso de negocio. BizTalk Server simplifica la implementación de estos escenarios separando conceptualmente los datos de la *hosts* que procesar los datos. A *host* es un contenedor lógico de BizTalk elementos, como orquestaciones, controladores de envío y controladores de recepción. Crear *instancias de host* y asignarlas al host. Una instancia de host es la representación física de un host en un servidor específico. Es el proceso del servicio de BizTalk Server llamado a BTSNTSvc.exe u otro proceso, por ejemplo, el proceso de IIS. Por lo que proporciona alta disponibilidad para el servidor BizTalk Server implica la ejecución de varios *instancias de host* y agrupación en clústeres las bases de datos de BizTalk Server, como se indica a continuación:  
  
-   **Arquitectura de Hosts de BizTalk**. BizTalk Server le permite separar hosts y ejecutar varias instancias de host para proporcionar alta disponibilidad para funciones clave como recibir mensajes, procesar orquestaciones y enviar mensajes. Estos hosts no requieren ningún adicionales de agrupación en clústeres o el mecanismo de equilibrio de carga porque BizTalk Server distribuye automáticamente la carga de trabajo entre varios equipos a través de instancias de host. Sin embargo, hospeda está ejecutando los controladores de recepción para los adaptadores de HTTP y SOAP requieren un mecanismo de equilibrio de carga como red equilibrio de carga (NLB) para proporcionar alta disponibilidad y hosts que ejecutan los controladores de recepción de FTP, MSMQ, POP3, SQL y SAP requieren una mecanismo de agrupación en clústeres para proporcionar alta disponibilidad.  
  
    > [!NOTE]  
    >  Siempre debe agrupar el SAP adaptador para dar cabida a un escenario de confirmación en dos fases de recepción.  
  
-   **Arquitectura de bases de datos de BizTalk Server**. Configuración de alta disponibilidad para las bases de datos de BizTalk Server normalmente consta de dos o más equipos de base de datos de SQL Server con una configuración de clúster activo/pasivo del servidor de. Estos equipos comparten un recurso de disco común (por ejemplo, una RAID 1 + 0 matriz de discos SCSI o una red de área de almacenamiento) y usar la agrupación en clústeres de conmutación por error de Windows para proporcionar copias de seguridad redundancia y tolerancia a errores.  
  
 Otro componente funcional de BizTalk que es crítico para la alta disponibilidad es el servidor secreto principal. BizTalk Server se basa en este servicio para obtener la clave de cifrado.  
  
 Esta sección proporciona información acerca de cómo obtener alta disponibilidad en cada una de estas categorías. Dado que una solución de alta disponibilidad de servidor BizTalk Server se basa en Windows y SQL Server, asegúrese de implementar estos productos con alta disponibilidad antes de configurar hosts de BizTalk Server. Los siguientes vínculos incluyen información sobre cómo proporcionar alta disponibilidad a estos productos subyacentes:  
  
-   **Soluciones de alta disponibilidad (SQL Server)] (https://docs.microsoft.com/sql/sql-server/failover-clusters/high-availability-solutions-sql-server)**  
  
-   **[Conmutación por error en Windows Server](https://docs.microsoft.com/windows-server/failover-clustering/failover-clustering-overview)**
  
## <a name="understanding-the-impact-of-a-component-failure"></a>Entender el impacto de un error de componente  
 En la tabla siguiente se enumera los componentes y las dependencias de un entorno de BizTalk Server y el impacto en el entorno de BizTalk Server si se produce un error en la dependencia o un componente. Debe considerar el ámbito de un posible error al decidir si desea una dependencia o un componente del clúster.  
  
|Dependencia o un componente|Ámbito del error|  
|-----------------------------|----------------------|  
|SQL Server|Todo el sistema. Si se produce un error de SQL Server, a continuación, BizTalk Server podrá procesar los documentos.|  
|Servidor secreto principal|Todo el sistema. Si se produce un error en el servidor secreto principal, a continuación, BizTalk Server podrá procesar los documentos. <br/>**Nota:** si se produce un error en el servidor secreto principal, cada servidor BizTalk server en el grupo de BizTalk continuarán utilizando una copia en memoria en caché del secreto principal hasta que se reinicie el servicio SSO empresarial en que BizTalk server. Si se reinicia el servicio SSO empresarial en los servidores BizTalk Server, la copia en caché del secreto principal se libera de la memoria y los servidores BizTalk Server deben ser capaz de ponerse en contacto con el servidor secreto principal para obtener otra copia del secreto principal. No se reinicie el servicio de SSO empresarial en los servidores de BizTalk en un grupo si se produce un error en el servidor secreto principal y desea que el servidor BizTalk server para continuar el procesamiento de documentos.|  
|MSDTC|Servidor. Si se produce un error de MSDTC se producirá un error en cualquier componente en el servidor que requiere compatibilidad con transacciones. <br/>**Nota:** porque SQL Server y el servidor secreto principal son dependientes de MSDTC para compatibilidad con transacciones, el ámbito del error se convertirá en todo el sistema si se produce un error en el MSDTC en el servidor SQL o el servidor secreto principal. BizTalk Server requiere compatibilidad con transacciones al comunicarse con SQL Server y el servidor secreto principal durante las operaciones de tiempo de ejecución.|  
|Instancia de host de BizTalk|Servidor. Todos los componentes alojados en una instancia de BizTalk Host podrá participar en el procesamiento de documentos si se produce un error en la instancia de host.|  
|Message Queue Server (MSMQ)|Servidor. Si MSMQ se produce un error, a continuación, cualquier procesamiento de documentos que depende el servicio MSMQ, como el adaptador de MSMQ, se detendrá en el servidor.|  
|Sistema de archivos|Servidor. Si se produce un error en el sistema de archivos, a continuación, cualquier procesamiento de documentos que depende el sistema de archivos, por ejemplo, el adaptador de archivo, se detendrá en el servidor.|  
  
 Para poder administrar mejor un sistema de BizTalk Server de alta disponibilidad, debe tener un buen conocimiento de la pila de BizTalk: Windows Server, controlador de dominio (DNS, DHCP), BizTalk Server, SQL Server, servidor IIS, servidor de archivos, servidor MSMQ, las aplicaciones externas. En esta sección se centra en la alta disponibilidad del servidor BizTalk Server y el equipo de SQL Server dependiente.  
  
## <a name="biztalk-server-high-availability-examples"></a>Ejemplos de alta disponibilidad de servidor BizTalk Server  
 Para escenarios de ejemplo de Microsoft BizTalk Server que proporcionan una alta disponibilidad mediante niveles de escala horizontal de hosts, consulte [escenarios de alta disponibilidad de ejemplo de BizTalk Server](../core/sample-biztalk-server-high-availability-scenarios.md).
  
## <a name="see-also"></a>Vea también  
 [Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)   
 [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [Lista de comprobación: aumento de la disponibilidad con la recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)