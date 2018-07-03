---
title: Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856e6bf882605737380f0bbe6185dce8a56c5828
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979613"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a><span data-ttu-id="a3279-102">Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a3279-102">Operations on functions and stored procedures in Oracle Database</span></span>
<span data-ttu-id="a3279-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con las funciones, procedimientos y paquetes de Oracle en la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a3279-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports Oracle functions, procedures, and packages in the following manner:</span></span>  
  
- <span data-ttu-id="a3279-104">**Funciones** se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="a3279-104">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="a3279-105">El nombre de la operación es el nombre de la función de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a3279-105">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="a3279-106">IN, OUT y en espera parámetros son compatibles, además, los valores devuelvan.</span><span class="sxs-lookup"><span data-stu-id="a3279-106">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
- <span data-ttu-id="a3279-107">**Procedimientos** se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="a3279-107">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="a3279-108">El nombre de la operación es el nombre del procedimiento de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a3279-108">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="a3279-109">Se admiten parámetros IN, OUT y en espera.</span><span class="sxs-lookup"><span data-stu-id="a3279-109">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
- <span data-ttu-id="a3279-110">**Empaqueta las funciones y procedimientos** se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="a3279-110">**Packaged functions and procedures** are surfaced as operations.</span></span> <span data-ttu-id="a3279-111">El nombre y espacio de nombres de la operación (función o procedimiento) está calificada por el nombre del paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a3279-111">The name and namespace of the operation (function or procedure) is qualified by the name of the Oracle package.</span></span> <span data-ttu-id="a3279-112">Se admiten las sobrecargas en paquetes (vea la siguiente viñeta).</span><span class="sxs-lookup"><span data-stu-id="a3279-112">Overloads are supported in packages (see next bullet).</span></span>  
  
- <span data-ttu-id="a3279-113">**Sobrecargar funciones y procedimientos** en paquetes que se exponen como operaciones.</span><span class="sxs-lookup"><span data-stu-id="a3279-113">**Overloaded functions and procedures** in packages are surfaced as operations.</span></span> <span data-ttu-id="a3279-114">Cada función sobrecargada o procedimiento aparece con una cadena que se anexa al nombre que identifica la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="a3279-114">Each overloaded function or procedure is surfaced with a string appended to its name that identifies the overload.</span></span> <span data-ttu-id="a3279-115">Esta cadena es parte de la secuencia "overload1", "overload2", "overload3" y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="a3279-115">This string is part of the sequence "overload1", "overload2", "overload3", and so on.</span></span>  
  
- <span data-ttu-id="a3279-116">**Tipos de REF CURSOR** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores.</span><span class="sxs-lookup"><span data-stu-id="a3279-116">**REF CURSOR types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="a3279-117">Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span><span class="sxs-lookup"><span data-stu-id="a3279-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
- <span data-ttu-id="a3279-118">**Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores.</span><span class="sxs-lookup"><span data-stu-id="a3279-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="a3279-119">Se admiten tipos de registros (anidados) simples y complejos.</span><span class="sxs-lookup"><span data-stu-id="a3279-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="a3279-120">Operaciones en funciones y procedimientos con tipos RECORD</span><span class="sxs-lookup"><span data-stu-id="a3279-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
  <span data-ttu-id="a3279-121">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="a3279-121">For more information about:</span></span>  
  
- <span data-ttu-id="a3279-122">Invocar un procedimiento de Oracle o una función mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos de la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) y [invocar sobrecargar funciones y procedimientos de uso de la base de datos de Oracle BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="a3279-122">Invoking an Oracle procedure or function by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) and [Invoke Overload Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="a3279-123">Invocar un procedimiento de Oracle o una función con el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="a3279-123">Invoking an Oracle procedure or function by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="a3279-124">Invocar un procedimiento de Oracle o una función con el modelo de canal WCF, vea [invocar una función de base de datos de Oracle mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="a3279-124">Invoking an Oracle procedure or function by using the WCF channel model, see [Invoke a Function in Oracle Database using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
- <span data-ttu-id="a3279-125">Estructura y las acciones de SOAP utilizadas para invocar funciones y procedimientos de Oracle, vea mensajes [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a3279-125">Message structure and SOAP actions used to invoke Oracle procedures and functions, see [Message Schemas for Functions and Procedures](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3279-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3279-126">See Also</span></span>  
 <span data-ttu-id="a3279-127">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a3279-127">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>