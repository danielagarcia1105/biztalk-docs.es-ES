---
title: Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f3b863-da3c-45b0-98f2-469a62286ebf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f693b676c1e3c0675051e9d0faf685e8b9d8df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021192"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] proporciona admite para los siguientes tipos de datos de gran tamaño de SQL Server:  
  
- Varchar (max)  
  
- Nvarchar (max)  
  
- Varbinary (max)  
  
  Para leer valores de datos grandes de SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de selección.  
  
  Para escribir valores de datos de gran tamaño en SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de establecimiento < nombre_columna >, donde < nombre_columna > es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max). La operación de establecimiento < nombre_columna > también permite a los clientes del adaptador escribir datos FILESTREAM en SQL Server 2008.  
  
> [!NOTE]
>  La operación de establecimiento < nombre_columna > está disponible solo para las tablas y vistas que contienen columnas con cualquiera de los tres tipos de datos de gran tamaño que se ha mencionado anteriormente.  
  
 Para obtener información detallada sobre cómo realizar operaciones en tablas y vistas en SQL Server que contienen tipos de datos grandes, consulte [operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)