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
# <a name="operations-on-tables-and-views-that-contain-large-data-types-using-the-sql-adapter"></a><span data-ttu-id="ab3f5-102">Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="ab3f5-102">Operations on tables and views that contain large data types using the SQL adapter</span></span>
<span data-ttu-id="ab3f5-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] proporciona admite para los siguientes tipos de datos de gran tamaño de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ab3f5-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides supports for the following SQL Server large data types:</span></span>  
  
- <span data-ttu-id="ab3f5-104">Varchar (max)</span><span class="sxs-lookup"><span data-stu-id="ab3f5-104">Varchar(Max)</span></span>  
  
- <span data-ttu-id="ab3f5-105">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ab3f5-105">Nvarchar(Max)</span></span>  
  
- <span data-ttu-id="ab3f5-106">Varbinary (max)</span><span class="sxs-lookup"><span data-stu-id="ab3f5-106">Varbinary(Max)</span></span>  
  
  <span data-ttu-id="ab3f5-107">Para leer valores de datos grandes de SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de selección.</span><span class="sxs-lookup"><span data-stu-id="ab3f5-107">To read large data values from SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Select operation.</span></span>  
  
  <span data-ttu-id="ab3f5-108">Para escribir valores de datos de gran tamaño en SQL Server, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la operación de establecimiento < nombre_columna >, donde < nombre_columna > es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="ab3f5-108">To write large data values to SQL Server, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the Set<column_name> operation, where <column_name> is the name of the column of type Varchar(Max), Nvarchar(Max) or Varbinary(Max).</span></span> <span data-ttu-id="ab3f5-109">La operación de establecimiento < nombre_columna > también permite a los clientes del adaptador escribir datos FILESTREAM en SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ab3f5-109">The Set<column_name> operation also allows adapter clients to write FILESTREAM data in SQL Server 2008.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab3f5-110">La operación de establecimiento < nombre_columna > está disponible solo para las tablas y vistas que contienen columnas con cualquiera de los tres tipos de datos de gran tamaño que se ha mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ab3f5-110">The Set<column_name> operation is available only for those tables and views that contain columns with any of the three large data types mentioned earlier.</span></span>  
  
 <span data-ttu-id="ab3f5-111">Para obtener información detallada sobre cómo realizar operaciones en tablas y vistas en SQL Server que contienen tipos de datos grandes, consulte [operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="ab3f5-111">For detailed information about performing operations on tables and views in SQL Server that contain large data types, see [Operations on tables and views that contain large data types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3f5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab3f5-112">See Also</span></span>  
 [<span data-ttu-id="ab3f5-113">Conectarse a un sistema SAP mediante el adaptador</span><span class="sxs-lookup"><span data-stu-id="ab3f5-113">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)