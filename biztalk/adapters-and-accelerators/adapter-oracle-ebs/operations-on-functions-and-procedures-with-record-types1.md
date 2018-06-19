---
title: Operaciones en funciones y procedimientos con registros Types1 | Documentos de Microsoft
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
ms.openlocfilehash: 43974d1c392a357b9781ff7f6fae5286e282513a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216084"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a><span data-ttu-id="8a882-102">Operaciones en funciones y procedimientos con tipos de registro</span><span class="sxs-lookup"><span data-stu-id="8a882-102">Operations on Functions and Procedures with RECORD Types</span></span>
<span data-ttu-id="8a882-103">Tipos de registros de Oracle se usan para representar la información jerárquica de parámetros pasados a los procedimientos y funciones de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="8a882-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="8a882-104">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos.</span><span class="sxs-lookup"><span data-stu-id="8a882-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> 

## <a name="supported-record-types"></a><span data-ttu-id="8a882-105">Tipos admitidos de registro</span><span class="sxs-lookup"><span data-stu-id="8a882-105">Supported RECORD types</span></span>
<span data-ttu-id="8a882-106">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con los siguientes tipos de tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="8a882-106">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the following kinds of RECORD types:</span></span>  
  
-   <span data-ttu-id="8a882-107">Tipos de registro que se declaran como tabla % ROWTYPE parámetros en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="8a882-107">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="8a882-108">Tipos de registro que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="8a882-108">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages.</span></span> <span data-ttu-id="8a882-109">Por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="8a882-109">For example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
-   <span data-ttu-id="8a882-110">Tipos de registros que contienen registros anidados.</span><span class="sxs-lookup"><span data-stu-id="8a882-110">RECORD types that contain nested records.</span></span>  
  
-   <span data-ttu-id="8a882-111">Tipos de registro que aparecen como IN, OUT o IN los parámetros OUT procedimientos o funciones.</span><span class="sxs-lookup"><span data-stu-id="8a882-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
-   <span data-ttu-id="8a882-112">Tipos de registros que son los valores devueltos de funciones.</span><span class="sxs-lookup"><span data-stu-id="8a882-112">RECORD types that are RETURN values of functions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a882-113">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no admite tipos BFILE como miembros de registro.</span><span class="sxs-lookup"><span data-stu-id="8a882-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a882-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a882-114">See Also</span></span>  
 <span data-ttu-id="8a882-115">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="8a882-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>