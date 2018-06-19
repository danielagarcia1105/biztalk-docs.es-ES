---
title: Optimizar el rendimiento de la base de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe9148c5b14c5c915de9a8d16699856922e051a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298732"
---
# <a name="optimizing-database-performance"></a>Optimizar el rendimiento de la base de datos
BizTalk Server es una aplicación de base de datos consume que requieran la creación de hasta 13 bases de datos de SQL Server. Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC. Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.  
  
 Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server. Para obtener más información sobre cómo optimizar el rendimiento de la base de datos de BizTalk, consulte la [notas del producto optimización de base de datos de BizTalk](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [Optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [Script de SQL de grupos de archivos de base de datos de cuadro de mensajes de servidor BizTalk Server](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [Supervisión del rendimiento de SQL Server](../technical-guides/monitoring-sql-server-performance.md)