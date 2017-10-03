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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783c09b1155202ac8fe5a964d16c24d33082c26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-optimizations"></a>Optimizaciones de SQL Server
BizTalk Server es una muy base de datos intensivas aplicación que requieran la creación de hasta 13 bases de datos de SQL Server. Dado que uno de los objetivos principales de diseño de BizTalk Server es garantizar que ningún mensaje se pierdan, BizTalk Server conserva los datos en el disco con gran frecuencia y además, lo hace en el contexto de una transacción MSDTC. Por lo tanto, el rendimiento de la base de datos tiene gran importancia para el rendimiento general de cualquier solución de BizTalk Server.  
  
 Esta sección describen métodos generales para maximizar el rendimiento de SQL Server, así como métodos para maximizar el rendimiento de la base de datos que son específicos de un entorno de BizTalk Server. Para obtener información adicional acerca de cómo optimizar BizTalk rendimiento de base de datos, vea el artículo de TechNet de optimización de base de datos de BizTalk en [http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Base de datos de configuración previa Optimizations1](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [Configuración posterior a la base de datos Optimizations1](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [Optimizar los grupos de archivos para el Databases1](../technical-guides/optimizing-filegroups-for-the-databases1.md)