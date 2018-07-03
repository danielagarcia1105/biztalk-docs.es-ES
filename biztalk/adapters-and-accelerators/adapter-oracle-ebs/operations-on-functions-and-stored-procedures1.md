---
title: Operaciones en funciones y almacenado Procedures1 | Microsoft Docs
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
ms.openlocfilehash: 3356b41fc7929c55794c65e804245ed231b19b18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007829"
---
# <a name="operations-on-functions-and-stored-procedures"></a><span data-ttu-id="83778-102">Operaciones en funciones y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="83778-102">Operations on Functions and Stored Procedures</span></span>
<span data-ttu-id="83778-103">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite Oracle funciones y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="83778-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures.</span></span>

## <a name="functions-and-procedures"></a><span data-ttu-id="83778-104">Funciones y procedimientos</span><span class="sxs-lookup"><span data-stu-id="83778-104">Functions and procedures</span></span>

<span data-ttu-id="83778-105">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] admite Oracle funciones y procedimientos de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="83778-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures in the following manner:</span></span>  
  
- <span data-ttu-id="83778-106">**Funciones** se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="83778-106">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="83778-107">El nombre de la operación es el nombre de la función de Oracle.</span><span class="sxs-lookup"><span data-stu-id="83778-107">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="83778-108">IN, OUT y en espera parámetros son compatibles, además, los valores devuelvan.</span><span class="sxs-lookup"><span data-stu-id="83778-108">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="83778-109">Si se pasa un parámetro no válido en una función (es decir, pasar un valor de cadena de un campo numérico), el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] podría producir una excepción según el comportamiento ODP.NET.</span><span class="sxs-lookup"><span data-stu-id="83778-109">If you pass an invalid parameter in a function (that is, pass a string value for a numeric field), the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] might throw an exception depending on the ODP.NET behavior.</span></span> <span data-ttu-id="83778-110">Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="83778-110">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite.</span></span>  
  
- <span data-ttu-id="83778-111">**Procedimientos** se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="83778-111">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="83778-112">El nombre de la operación es el nombre del procedimiento de Oracle.</span><span class="sxs-lookup"><span data-stu-id="83778-112">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="83778-113">Se admiten parámetros IN, OUT y en espera.</span><span class="sxs-lookup"><span data-stu-id="83778-113">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="83778-114">Como parte de un procedimiento, si insertar o actualizar un valor decimal (por ejemplo, 15.2) en un campo numérico de una tabla de interfaz o la tabla de base de datos, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="83778-114">As part of a procedure, if you insert or update a decimal value (for example, 15.2) into a numeric field of an interface table or database table, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span> <span data-ttu-id="83778-115">Esto es porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa ODP.NET para comunicarse con Oracle E-Business Suite y ODP.NET no admite aceptando los valores decimales para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="83778-115">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite, and ODP.NET does not support accepting decimal values for the numeric fields.</span></span>  
  
- <span data-ttu-id="83778-116">**Tipos de REF CURSOR** son compatibles con IN y OUT parámetros para procedimientos y funciones, así como para la función de los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="83778-116">**REF CURSOR types** are supported for IN and OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="83778-117">Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span><span class="sxs-lookup"><span data-stu-id="83778-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
- <span data-ttu-id="83778-118">**Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores.</span><span class="sxs-lookup"><span data-stu-id="83778-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="83778-119">Se admiten tipos de registros (anidados) simples y complejos.</span><span class="sxs-lookup"><span data-stu-id="83778-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="83778-120">Operaciones en funciones y procedimientos con tipos RECORD</span><span class="sxs-lookup"><span data-stu-id="83778-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  <span data-ttu-id="83778-121">También puede establecer el contexto de la aplicación para las funciones y procedimientos almacenados en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83778-121">You can also set the application context for functions and stored procedures in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="83778-122">Para obtener información sobre el contexto de la aplicación y cómo configurarlo, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="83778-122">For information about application context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83778-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="83778-123">See Also</span></span>  
 <span data-ttu-id="83778-124">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="83778-124">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>