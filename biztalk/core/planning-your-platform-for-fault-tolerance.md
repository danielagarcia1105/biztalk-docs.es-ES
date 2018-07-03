---
title: Planear la plataforma para tolerancia a errores | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- MessageBox database, fault tolerance
- clustering, fault tolerance
- SQL Server RAID
- databases [BAM], fault tolerance
- BizTalk Server, planning
- fault tolerance
- clustering, fail-overs
- planning, fault tolerance
- Primary Import database [BAM]
- BizTalk Server, backing up
- fault tolerance, planning
- planning, BizTalk Server
- Primary Import database [BAM], fault tolerance
- fail-over clustering
ms.assetid: 512ed6b8-db1e-434a-8009-63e952cf5500
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ddc4565449171c71685bcddd2c68b699f5113b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007493"
---
# <a name="planning-your-platform-for-fault-tolerance"></a>Planear la plataforma para tolerancia a errores
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está basado en las plataformas Microsoft Windows y Microsoft SQL Server. La capacidad de BizTalk Server de sobrevivir o recuperarse de un desastre depende de la capacidad de supervivencia o recuperación de la plataforma subyacente.  
  
 Para las bases de datos de supervisión de la actividad económica (BAM) y la base de datos de cuadro de mensajes, se recomienda que realice lo siguiente:  
  
- Configure la agrupación de conmutación por error, disponible en SQL Server Enterprise Edition. La agrupación de conmutación por error permite a SQL Server cambiar automáticamente el procesamiento de una instancia de SQL Server de un servidor que ha dejado de funcionar a un servidor en funcionamiento.  
  
   La base de datos de importación principal de BAM recopila datos de eventos. Si se produce un desastre, se perderán los datos que se hayan escrito en la base de datos de importación principal de BAM desde la última copia de seguridad. Puesto que no hay forma de regenerar los eventos perdidos, es especialmente importante habilitar la agrupación de conmutación por error en la base de datos de importación principal de BAM  
  
- Utilice la matriz redundante de discos independientes (RAID) de SQL Server, especialmente para las bases de datos de cuadros de mensajes y de importación principal de BAM.  
  
  Utilice los recursos siguientes para diseñar las implementaciones de Windows y SQL Server con tolerancia a errores. Dedique el tiempo que sea necesario a obtener información sobre las tecnologías de redundancia de servidores y hardware, como la agrupación y el reflejo de disco, para prevenir las interrupciones del servicio y la pérdida de datos.  
  
- [Notas del producto: Alta disponibilidad, las tecnologías de AlwaysOn](http://go.microsoft.com/fwlink/?LinkId=130376)  
  
   Las notas del producto “ High Availability – Always On Technologies” describen las funciones de alta disponibilidad que se encuentran disponibles con SQL Server 2008.  
  
- [Información general sobre soluciones de alta disponibilidad](http://go.microsoft.com/fwlink/?LinkId=130377)  
  
   Introduce varias soluciones de alta disponibilidad para SQL Server 2008 que mejoran la disponibilidades de servidores o bases de datos.  
  
- [Kit de recursos de capítulo 15: opciones de alta disponibilidad, SQL Server](http://go.microsoft.com/fwlink/?LinkId=24431)  
  
   El Kit de recursos de Microsoft SQL Server abarca una amplia gama de áreas de planeamiento administrativo y de implementación. En el capítulo 15, se trata el planeamiento de la recuperación y la tolerancia a errores.  
  
- [Guía paso a paso de servicios de implementación de Windows](http://go.microsoft.com/fwlink/?LinkId=130379)  
  
   Contiene instrucciones paso a paso sobre el uso del rol Servicios de implementación de Windows en Windows Server 2008  
  
- [Kit de implementación de Windows Server 2003: Planeación de implementaciones de servidor](http://go.microsoft.com/fwlink/?LinkId=24433).  
  
   Este libro contiene información sobre cómo planear el almacenamiento en servidores y sobre el diseño y la implementación de servidores de archivos, servidores de impresión y servidores de Terminal Server en organizaciones de mediano y gran tamaño.  
  
   También puede usar las instrucciones de este libro para planear la administración de servidores remotos, diseñar e implementar clústeres de servidores, y diseñar e implementar clústeres de equilibrio de carga de red con el fin de maximizar la disponibilidad y la escalabilidad de los servidores.  
  
## <a name="backing-up-your-platform"></a>Copia de seguridad de la plataforma  
 Una vez configurado el sistema, prepare copias de seguridad completas de los servidores para poder restablecer rápidamente un servidor idéntico en caso de pérdida de datos.  
  
 Para realizar una copia de seguridad de la plataforma, siga los procedimientos de copia de seguridad documentados para cada una de las tecnologías siguientes:  
  
- Microsoft Windows Server Standard, Enterprise o Datacenter Edition  
  
- Servicios de Internet Information Server (IIS)  
  
- Microsoft SQL Server  
  
- Windows SharePoint Services, que es usado por el adaptador de los servicios de Windows SharePoint.  
  
  Siga las recomendaciones de la "Guía de operaciones de BizTalk Server" para "Backing up BizTalk Server" disponible en [lista de comprobación: aumento de disponibilidad con recuperación ante desastres](http://go.microsoft.com/fwlink/?LinkId=130498).  
  
  Pruebe exhaustivamente los procedimientos de copia de seguridad y restauración, y colóquelos en una ubicación segura y remota.  
  
## <a name="see-also"></a>Vea también  
 [Realizar una copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md)