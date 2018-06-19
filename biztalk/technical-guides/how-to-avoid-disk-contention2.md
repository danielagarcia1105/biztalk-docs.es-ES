---
title: Cómo evitar disco Contention2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37bdf6bd-cb34-4540-819e-908d83a22d40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7be7a38ac3f3f6cc1d7d266c664cbb85f731c22
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "22298140"
---
# <a name="how-to-avoid-disk-contention"></a>Cómo evitar la contención del disco
BizTalk Server está diseñado como un sistema permanente. Para escenarios de alto rendimiento, las bases de datos de cuadro de mensaje y seguimiento de BizTalk pueden sufrir contenciones severas. Esta contención puede verse agravada por discos lentos. Si los discos son lenta (mayor que 15 ms en promedio para el tiempo medio En segundos/lectura o AVG. En segundos/escritura en disco), es posible que SQL Server para almacenar bloqueos durante más tiempo (tiempo de espera de bloqueo de alta y alta tiempos de espera de bloqueo). Esto, a su vez, puede producir las tablas de cuadro de mensajes (cola de impresión y colas de aplicaciones) a crecer, provocando inundación de base de datos y la limitación. Esta situación se produce en última instancia en el rendimiento global sostenible inferior.  
  
> [!NOTE]  
>  Para obtener información acerca de cómo identificar si un servidor tiene un cuello de botella de disco, consulte [Monitor de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkID=204007) (http://go.microsoft.com/fwlink/?LinkID=204007). Monitor de rendimiento de Windows es un complemento de Microsoft Management Console (MMC) que proporciona herramientas para analizar el rendimiento del sistema.  
  
 Para evitar la contención de disco, haga lo siguiente:  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Usar Raid10 / 0 + configuraciones de 1 disco.|[Procedimientos recomendados para evitar cuellos de botella](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|Si es posible, implemente las bases de datos en una SAN de alta velocidad. Si varias bases de datos comparten los mismos discos, se recomienda configurarlos en diferente **dedicado** discos. Además, se recomienda separar los archivos MDF y LDF para la base de datos de cuadro de mensajes en diferentes discos.|[Optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md)|  
|Considere la posibilidad de asignar varios archivos para la base de datos TEMPDB, ya que esto borrará significativamente reducir la contención de disco y repartir la carga entre varios archivos de datos.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Considere la posibilidad de separar la base de datos de cuadro de mensajes en un servidor dedicado que es independiente de las bases de datos de seguimiento de BizTalk.|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Asignar el directorio de archivos de registro MSDTC a un disco dedicado independiente.|[Optimización del rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)|  
|Si hay contención en la unidad local debido al archivo de paginación o al registro MSDTC, intente moverlos a una unidad independiente.|[Procedimientos recomendados para evitar cuellos de botella](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|Optimizar la base de datos de seguimiento para las operaciones de escritura.|[Cómo identificar cuellos de botella en la base de datos de seguimiento](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)|  
|Optimizar la base de datos de cuadro de mensajes para lectura y las operaciones de escritura.|[Cómo identificar cuellos de botella en el cuadro de mensajes Database1](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)|  
|Si una instancia de host de BizTalk sature la CPU, considere la posibilidad de separar enviar, recibir, procesar y funcionalidad de seguimiento en varios hosts. Esto configura el sistema para que la funcionalidad de orquestación se ejecuta en un servidor dedicado independiente para mejorar el rendimiento global del sistema.|[Optimización del rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)|  
|Si se implementan varias orquestaciones, considere la posibilidad de ellos la inscripción en hosts de orquestación dedicados diferentes. Esto aísla las distintas orquestaciones y evita la contención de recursos compartidos en el mismo espacio de dirección física o en el mismo servidor.|[Optimización del rendimiento de BizTalk Server](../technical-guides/optimizing-biztalk-server-performance.md)|  
|Considere la posibilidad de usar Monitor de rendimiento de Windows para diagnosticar problemas de contención de disco...|[Monitor de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkID=204007)|  
  
 Para obtener más información sobre el análisis de rendimiento de disco, vea los siguientes recursos:  
  
-   [Excluir Disk-Bound Problems](http://go.microsoft.com/fwlink/?LinkId=120947) (HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=120947" \t "_blank"http://go.microsoft.com/fwlink/?LinkId=120947).  
  
-   [Procedimientos recomendados de E/S previas a la implementación de SQL Server](http://go.microsoft.com/fwlink/?LinkId=120948) (http://go.microsoft.com/fwlink/?LinkId=120948).  
  
-   Sección "Cuellos de botella de E/S" de [solucionar problemas de rendimiento en SQL Server 2008](http://go.microsoft.com/fwlink/?LinkID=153586) (http://go.microsoft.com/fwlink/?LinkID=153586).  
  
## <a name="see-also"></a>Vea también  
 [Cuellos de botella en el nivel de base de datos](../technical-guides/bottlenecks-in-the-database-tier.md)