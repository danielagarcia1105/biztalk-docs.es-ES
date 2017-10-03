---
title: Solucionar problemas de rendimiento con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b0f8db3f1b7549f6189b348b7353d6dac159a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a>Solucionar problemas de rendimiento con el adaptador de la base de datos de Oracle
Esta sección describe el uso de técnicas de solución de problemas para resolver los problemas de rendimiento que pueden surgir al usar [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
## <a name="known-issue"></a>Problema conocido  
 Éste es el problema de rendimiento más comunes que pueden surgir al usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], junto con su causa y resolución.  
  
##  <a name="BKMK_Slowdown"></a>Degradación o pausa en el rendimiento al usar el adaptador con BizTalk Server  
 **Problema**  
  
 Cuando se usa el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el número de mensajes enviados o recibidos por el adaptador se ralentiza o se trata de una pausa.  
  
 **Causa**  
  
 El **EnableBizTalkCompatibilityMode** no está establecida la propiedad de enlace en WCF-Custom enviar o puerto de recepción en la consola de administración de BizTalk Server.  
  
 **Resolución**  
  
 Establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en True. Para obtener más información acerca de esta propiedad, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md). Para obtener instrucciones sobre cómo establecer una propiedad de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a>Posible pérdida de memoria en un equipo de 64 bits cuando se usa el adaptador de la base de datos de Oracle para realizar operaciones relacionadas con el tipo de datos FLOAT  
 **Problema**  
  
 Puede experimentar una pérdida de memoria cuando se usa el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en un equipo de 64 bits para realizar las operaciones que implican tipos de datos FLOAT.  
  
 **Resolución**  
  
 Instale .NET \< *versión*> (x64) en el equipo de 64 bits.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del Oracle adapter.md la base de datos](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)