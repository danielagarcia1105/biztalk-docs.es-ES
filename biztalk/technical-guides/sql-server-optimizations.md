---
title: Optimizaciones de SQL Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36317d99387fde1d7b5e1c56b45255129daedb25
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="sql-server-optimizations"></a>Optimizaciones de SQL Server
BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos de SQL Server. Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC. Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.  
  
Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server. Los vínculos siguientes también son buenos recursos: 

- [El servidor BizTalk Server: Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [Guía de optimización del rendimiento de BizTalk Server](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Optimizaciones de base de datos previas a la configuración](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [Optimizaciones de base de datos después de la configuración](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [Optimización de grupos de archivos para las bases de datos](../technical-guides/optimizing-filegroups-for-the-databases1.md)