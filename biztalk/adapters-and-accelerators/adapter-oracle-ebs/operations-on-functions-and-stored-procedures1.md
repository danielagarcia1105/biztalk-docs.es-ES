---
title: Operaciones en las funciones y almacenado Procedures1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfe5f705c8e432c920c8fae41a2b2f050c188047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216356"
---
# <a name="operations-on-functions-and-stored-procedures"></a><span data-ttu-id="980e8-102">Operaciones en funciones y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="980e8-102">Operations on Functions and Stored Procedures</span></span>
<span data-ttu-id="980e8-103">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con los procedimientos y funciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="980e8-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures.</span></span>

## <a name="functions-and-procedures"></a><span data-ttu-id="980e8-104">Funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="980e8-104">Functions and procedures</span></span>

<span data-ttu-id="980e8-105">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es compatible con las funciones de Oracle y los procedimientos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="980e8-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures in the following manner:</span></span>  
  
-   <span data-ttu-id="980e8-106">**Funciones** aparecen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="980e8-106">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="980e8-107">El nombre de la operación es el nombre de la función de Oracle.</span><span class="sxs-lookup"><span data-stu-id="980e8-107">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="980e8-108">EN fuera y en espera parámetros son compatibles, así como, valores devuelvan.</span><span class="sxs-lookup"><span data-stu-id="980e8-108">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="980e8-109">Si se pasa un parámetro no válido en una función (es decir, pasar un valor de cadena de un campo numérico), el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] podría producir una excepción según el comportamiento ODP.NET.</span><span class="sxs-lookup"><span data-stu-id="980e8-109">If you pass an invalid parameter in a function (that is, pass a string value for a numeric field), the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] might throw an exception depending on the ODP.NET behavior.</span></span> <span data-ttu-id="980e8-110">Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="980e8-110">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite.</span></span>  
  
-   <span data-ttu-id="980e8-111">**Procedimientos** aparecen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="980e8-111">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="980e8-112">El nombre de la operación es el nombre del procedimiento de Oracle.</span><span class="sxs-lookup"><span data-stu-id="980e8-112">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="980e8-113">Se admiten parámetros en fuera y en espera.</span><span class="sxs-lookup"><span data-stu-id="980e8-113">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="980e8-114">Como parte de un procedimiento, si inserta o actualiza un valor decimal (por ejemplo, 15,2) en un campo numérico de una tabla de interfaz o una tabla de base de datos, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="980e8-114">As part of a procedure, if you insert or update a decimal value (for example, 15.2) into a numeric field of an interface table or database table, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span> <span data-ttu-id="980e8-115">Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza ODP.NET para comunicarse con Oracle E-Business Suite y ODP.NET no admite aceptando los valores decimales para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="980e8-115">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite, and ODP.NET does not support accepting decimal values for the numeric fields.</span></span>  
  
-   <span data-ttu-id="980e8-116">**Tipos de REF CURSOR** son compatibles con IN y OUT parámetros para los procedimientos y funciones, así como para la función de los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="980e8-116">**REF CURSOR types** are supported for IN and OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="980e8-117">Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span><span class="sxs-lookup"><span data-stu-id="980e8-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
-   <span data-ttu-id="980e8-118">**Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT DEVUELVEN valores.</span><span class="sxs-lookup"><span data-stu-id="980e8-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="980e8-119">Se admiten tipos de registros (anidados) simples y complejos.</span><span class="sxs-lookup"><span data-stu-id="980e8-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="980e8-120">Operaciones en funciones y procedimientos con tipos de registro</span><span class="sxs-lookup"><span data-stu-id="980e8-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  <span data-ttu-id="980e8-121">También puede establecer el contexto de la aplicación para las funciones y procedimientos almacenados en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="980e8-121">You can also set the application context for functions and stored procedures in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="980e8-122">Para obtener información sobre el contexto de la aplicación y cómo configurarlo, vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="980e8-122">For information about application context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980e8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="980e8-123">See Also</span></span>  
 <span data-ttu-id="980e8-124">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="980e8-124">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>