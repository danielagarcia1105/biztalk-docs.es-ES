---
title: Supervisión y reducción la contención de E/S de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4a58b0733f44ca2d85c96a9b4a91045bb3947be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001109"
---
# <a name="monitoring-and-reducing-database-io-contention"></a>Supervisión y reducción de la contención de E/S de la base de datos
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rendimiento a menudo se basa en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] rendimiento, lo que a su vez a menudo se basa en el rendimiento de E/S de disco. Por lo tanto, debe supervisar y ajustar el rendimiento de E/S de disco en los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] casa el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
## <a name="monitoring-disk-io"></a>Supervisión de E/S de disco  
 Dada la naturaleza de la base de datos intensivo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], E/S de disco pueden convertirse fácilmente en un cuello de botella en el cuadro de mensajes y BizTalk seguimiento de las bases de datos; esto es cierto incluso si la E/S de disco no ha sido previamente un cuello de botella para los archivos de base de datos en su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] entorno. Por lo tanto, se recomienda que proactivamente medir el rendimiento de E/S de disco para los discos que hospedan los archivos de registro de transacciones y de datos. Para obtener más información sobre la supervisión de rendimiento de E/S de disco mediante el Monitor de sistema, consulte el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] artículo ["Prácticas recomendadas de E/S de preimplementación"](http://go.microsoft.com/fwlink/?LinkId=104829) (<http://go.microsoft.com/fwlink/?LinkId=104829>). Si usa una SAN, también necesite herramientas específicas del fabricante del hardware de SAN para medir el rendimiento de E/S del disco.  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>Separa el cuadro de mensajes y las bases de datos (DTA) y los archivos de registro de seguimiento de BizTalk  
 Puesto que las bases de datos de cuadro de mensaje y seguimiento de BizTalk son los más activos, se recomienda colocar los archivos de datos y los archivos de registro de transacciones para cada una de ellas en unidades de disco dedicados para reducir la probabilidad de problemas de contención de E/S de disco. Por ejemplo, necesitaría cuatro unidades de disco para los archivos de base de datos de cuadro de mensajes y seguimiento de BizTalk; una unidad para cada una de las siguientes acciones:  
  
- Archivos de datos de cuadro de mensajes  
  
- Archivos de registro de transacciones de cuadro de mensajes  
  
- Archivos de datos de seguimiento de BizTalk  
  
- Archivos de registro de transacciones de seguimiento de BizTalk  
  
  Separar las bases de datos de cuadro de mensaje y seguimiento de BizTalk y separación de los archivos de base de datos y archivos de registro de transacciones en discos físicos diferentes se consideran mejores prácticas para reducir la contención de E/S de disco. Pruebe a distribuir la E/S de disco en ejes físicos tantos como sea posible. Para obtener más información sobre cómo evitar la contención del disco, consulte [cómo evitar la contención del disco](http://go.microsoft.com/fwlink/?LinkId=158809) (<http://go.microsoft.com/fwlink/?LinkId=158809>) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Guía de optimización del rendimiento.  
  
  Debe separar los archivos manualmente después de configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte el [notas de la optimización de base de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=101578) (<http://go.microsoft.com/fwlink/?LinkId=101578>).  
  
## <a name="see-also"></a>Vea también  
 [Uso de la herramienta Análisis de rendimiento de registros (PAL)](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)