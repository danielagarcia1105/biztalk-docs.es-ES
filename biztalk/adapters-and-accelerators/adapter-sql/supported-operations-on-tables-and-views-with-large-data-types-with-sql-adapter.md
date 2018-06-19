---
title: Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL | Documentos de Microsoft
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
ms.openlocfilehash: e1d6d2c52ce0772297bb2834c13f31a55d7b7a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223868"
---
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a>Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] proporciona admite para los siguientes tipos de datos de gran tamaño de SQL Server:  
  
-   Varchar (max)  
  
-   Nvarchar (max)  
  
-   Varbinary (max)  
  
 Para leer valores de datos grandes de SQL Server, la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de selección.  
  
 Para escribir valores de datos grandes en SQL Server, la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de establecimiento < column_name >, donde < column_name > es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max). La operación de establecimiento < column_name > también permite a los clientes de adaptador escribir los datos FILESTREAM en SQL Server 2008.  
  
> [!NOTE]
>  La operación de establecimiento < column_name > sólo está disponible para las tablas y vistas que contienen columnas con cualquiera de los tres tipos de datos de gran tamaño que se ha mencionado anteriormente.  
  
 Para obtener información detallada sobre cómo realizar operaciones en tablas y vistas de SQL Server que contienen tipos de datos de gran tamaño, vea [operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)