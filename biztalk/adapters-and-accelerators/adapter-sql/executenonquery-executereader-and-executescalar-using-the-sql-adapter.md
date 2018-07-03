---
title: Ejecutar ExecuteNonQuery, ExecuteReader y operaciones de ExecuteScalar mediante el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7374a0852c4f6689a0c092e5ddf0b11c038d6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990325"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a><span data-ttu-id="5cb9b-102">Ejecutar ExecuteNonQuery, ExecuteReader y operaciones de ExecuteScalar mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="5cb9b-102">Run ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations using the SQL adapter</span></span>
<span data-ttu-id="5cb9b-103">La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las siguientes operaciones en el nivel raíz:</span><span class="sxs-lookup"><span data-stu-id="5cb9b-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the following operations at the root level:</span></span>  
  
- <span data-ttu-id="5cb9b-104">**ExecuteNonQuery**: Use esta operación para ejecutar cualquier instrucción SQL arbitraria en SQL Server si no desea que cualquier conjunto de resultados a devolverse.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements in SQL Server if you do not want any result set to be returned.</span></span> <span data-ttu-id="5cb9b-105">Puede utilizar esta operación para crear objetos de base de datos o cambiar datos en una base de datos mediante la ejecución de UPDATE, INSERT o DELETE.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-105">You can use this operation to create database objects or change data in a database by executing UPDATE, INSERT, or DELETE statements.</span></span> <span data-ttu-id="5cb9b-106">El valor devuelto de esta operación es de tipo de datos Int32 y:</span><span class="sxs-lookup"><span data-stu-id="5cb9b-106">The return value of this operation is of Int32 data type, and:</span></span>  
  
  -   <span data-ttu-id="5cb9b-107">Para las instrucciones UPDATE, INSERT y DELETE, el valor devuelto es el número de filas afectadas por la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-107">For the UPDATE, INSERT, and DELETE statements, the return value is the number of rows affected by the SQL statement.</span></span>  
  
  -   <span data-ttu-id="5cb9b-108">Para los demás tipos de instrucciones, el valor devuelto es **-1**.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-108">For all other types of statements, the return value is **-1**.</span></span>  
  
- <span data-ttu-id="5cb9b-109">**ExecuteReader**: Use esta operación para ejecutar todas las instrucciones SQL arbitrarias en SQL Server si desea que el conjunto de resultados que se devolverán, si existe, como una matriz de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-109">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements in SQL Server if you want the result set to be returned, if any, as an array of DataSet.</span></span> <span data-ttu-id="5cb9b-110">Para obtener información sobre el conjunto de datos, vea "Clase de conjunto de datos" en [ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853).</span><span class="sxs-lookup"><span data-stu-id="5cb9b-110">For information about DataSet, see “DataSet Class” at [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).</span></span>  
  
- <span data-ttu-id="5cb9b-111">**ExecuteScalar**: Use esta operación para ejecutar cualquier instrucción SQL arbitraria en SQL Server para devolver un valor único.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-111">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements in SQL Server to return a single value.</span></span> <span data-ttu-id="5cb9b-112">Esta operación devuelve el valor solo en la primera columna de la primera fila del conjunto de resultados devuelto por la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-112">This operation returns the value only in the first column of the first row in the result set returned by the SQL statement.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5cb9b-113">La ventaja de ExecuteScalar sobre ExecuteReader es que la carga del mensaje de respuesta de la operación ExecuteScalar es mucho menor en comparación con el devuelto por la operación ExecuteReader.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-113">The advantage of ExecuteScalar over ExecuteReader is that the response message payload of the ExecuteScalar operation is much smaller compared to the one returned by the ExecuteReader operation.</span></span> <span data-ttu-id="5cb9b-114">Por lo tanto, si necesita solo un valor que se devolverá, debe usar ExecuteScalar en lugar de ExecuteReader.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-114">Therefore, if you require only one value to be returned, you should use ExecuteScalar instead of ExecuteReader.</span></span>  
  
  <span data-ttu-id="5cb9b-115">Puede usar la operación ExecuteNonQuery, ExecuteReader y ExecuteScalar para ejecutar varias instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="5cb9b-115">You can use the ExecuteNonQuery, ExecuteReader or ExecuteScalar operation to execute multiple SQL statements.</span></span>  
  
  <span data-ttu-id="5cb9b-116">Para obtener más información acerca de cómo realizar estas operaciones mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ExecuteReader, ExecuteScalar o ExecuteNonQuery las operaciones mediante BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="5cb9b-116">For more information about performing these operations using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb9b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb9b-117">See Also</span></span>  
 <span data-ttu-id="5cb9b-118">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="5cb9b-118">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>