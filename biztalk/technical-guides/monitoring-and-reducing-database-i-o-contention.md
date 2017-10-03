---
title: "Supervisión y reducir base de datos de contención de E/S | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 446a4b512b4f38869637cb3968305fad1e869dae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-and-reducing-database-io-contention"></a>Supervisión y reducir la contención de E/S de la base de datos
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]rendimiento a menudo se basa en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento, lo que a su vez a menudo se basa en el rendimiento de E/S de disco. Por lo tanto, debe supervisar y ajustar el rendimiento de E/S de disco en los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] esa casa el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
## <a name="monitoring-disk-io"></a>Supervisar la E/S del disco  
 Dada la naturaleza de la base de datos que utilizan mucha de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], E/S de disco pueden convertirse fácilmente en un cuello de botella en el cuadro de mensajes y BizTalk seguimiento bases de datos; esto es cierto incluso si la E/S de disco ahora no ha sido un cuello de botella para los archivos de base de datos en su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] entorno. Por lo tanto, se recomienda que proactivamente medir el rendimiento de E/S de disco para los discos que almacenan los archivos de registro de transacciones y de datos. Para obtener más información acerca de cómo supervisar el rendimiento de E/S de disco con el Monitor de sistema, consulte el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] artículo ["Prácticas recomendadas de E/S antes de la implementación"](http://go.microsoft.com/fwlink/?LinkId=104829) (http://go.microsoft.com/fwlink/?LinkId=104829). Si utilizas una SAN, también deberá herramientas específicas del fabricante del hardware de SAN para medir el rendimiento de E/S de disco.  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>Separa el cuadro de mensajes y las bases de datos (DTA) y archivos de registro de seguimiento de BizTalk  
 Puesto que las bases de datos de cuadro de mensaje y seguimiento de BizTalk son más activos, se recomienda colocar los archivos de datos y archivos de registro de transacciones para cada una de ellas en unidades dedicadas para reducir la probabilidad de problemas de contención de E/S de disco. Por ejemplo, necesitaría cuatro unidades de disco para los archivos de base de datos de cuadro de mensaje y seguimiento de BizTalk; una unidad para cada una de las siguientes acciones:  
  
-   Archivos de datos de cuadro de mensajes  
  
-   Archivos de registro de transacciones de cuadro de mensajes  
  
-   Archivos de datos de seguimiento de BizTalk  
  
-   Archivos de registro de transacciones de seguimiento de BizTalk  
  
 Separar las bases de datos de cuadro de mensaje y seguimiento de BizTalk y separar los archivos de base de datos y archivos de registro de transacciones en discos físicos diferentes se consideran prácticas recomendadas para reducir la contención de E/S de disco. Intente distribuir la E/S de disco en tantos ejes físicos como sea posible. Para obtener más información acerca de cómo evitar la contención de disco, consulte [cómo evitar la contención de disco](http://go.microsoft.com/fwlink/?LinkId=158809) (http://go.microsoft.com/fwlink/?LinkId=158809) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento.  
  
 Debe separar los archivos manualmente después de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte el [notas del producto BizTalk Server Database Optimization](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).  
  
## <a name="see-also"></a>Vea también  
 [Usar el análisis de rendimiento de la herramienta de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)