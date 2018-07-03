---
title: Operaciones en funciones y procedimientos con registros Types1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006437"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a><span data-ttu-id="59dad-102">Operaciones en funciones y procedimientos con tipos RECORD</span><span class="sxs-lookup"><span data-stu-id="59dad-102">Operations on Functions and Procedures with RECORD Types</span></span>
<span data-ttu-id="59dad-103">Tipos de registros de Oracle se usan para representar información jerárquica de los parámetros pasados a los procedimientos y funciones de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="59dad-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="59dad-104">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos.</span><span class="sxs-lookup"><span data-stu-id="59dad-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> 

## <a name="supported-record-types"></a><span data-ttu-id="59dad-105">Tipos admitidos de registro</span><span class="sxs-lookup"><span data-stu-id="59dad-105">Supported RECORD types</span></span>
<span data-ttu-id="59dad-106">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite los siguientes tipos de los tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="59dad-106">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="59dad-107">Tipos de registros que se declaran como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="59dad-107">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="59dad-108">Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="59dad-108">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages.</span></span> <span data-ttu-id="59dad-109">Por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="59dad-109">For example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="59dad-110">Tipos de registros que contienen registros anidados.</span><span class="sxs-lookup"><span data-stu-id="59dad-110">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="59dad-111">Tipos de registros que aparecen como IN, OUT o IN OUT parámetros a procedimientos o funciones.</span><span class="sxs-lookup"><span data-stu-id="59dad-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="59dad-112">Tipos de registros que son los valores devueltos de funciones.</span><span class="sxs-lookup"><span data-stu-id="59dad-112">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="59dad-113">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos BFILE como miembros de registro.</span><span class="sxs-lookup"><span data-stu-id="59dad-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59dad-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="59dad-114">See Also</span></span>  
 <span data-ttu-id="59dad-115">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="59dad-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>