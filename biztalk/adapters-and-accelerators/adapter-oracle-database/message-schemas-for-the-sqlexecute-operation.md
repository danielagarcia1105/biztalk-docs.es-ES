---
title: "Esquemas de mensaje para la operación SQLEXECUTE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7efc6a59e9dd4c163388803763a7b90a13b31
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a><span data-ttu-id="9e7fb-102">Esquemas de mensaje para la operación SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="9e7fb-102">Message Schemas for the SQLEXECUTE Operation</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="9e7fb-103">expone metadatos fuertemente tipada de artefactos presentes en el sistema LOB y expone las operaciones estándares de estos artefactos.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-103"> surfaces strongly-typed metadata for artifacts present in the LOB system and exposes standard operations on these artifacts.</span></span> <span data-ttu-id="9e7fb-104">Sin embargo, hay escenarios donde una aplicación puede requerir la ejecución de una instrucción SQL arbitraria que se controla mediante la lógica de negocios en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-104">However, there are scenarios where an application might require the execution of an arbitrary SQL statement that is driven by the business logic in the application.</span></span> <span data-ttu-id="9e7fb-105">Por ejemplo, puede:</span><span class="sxs-lookup"><span data-stu-id="9e7fb-105">For example, you may want to:</span></span>  
  
-   <span data-ttu-id="9e7fb-106">Realizar una operación en artefactos de base de datos que no se exponen a través de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtenga el CURVAL o NEXTVAL de las secuencias de Oracle.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-106">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
-   <span data-ttu-id="9e7fb-107">Realizar operaciones de lenguaje de definición de datos; Por ejemplo, crear una tabla.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-107">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
-   <span data-ttu-id="9e7fb-108">Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal que se crea mediante la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-108">Perform operations on a database artifact that was not present at design-time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
-   <span data-ttu-id="9e7fb-109">Realizar operaciones más complejas de DML en tablas que las operaciones obtenidas por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo realizar una consulta que incluya una cláusula de combinación.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-109">Perform more complex DML operations on tables than the operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example perform a query that includes a JOIN clause.</span></span>  
  
 <span data-ttu-id="9e7fb-110">La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone una operación especial que se llamó a la operación SQLEXECUTE para admitir estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces a special operation called the SQLEXECUTE operation to support such scenarios.</span></span> <span data-ttu-id="9e7fb-111">Mediante el uso de esta operación, puede especificar una instrucción SQL arbitraria para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para ejecutar en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-111">By using this operation, you can specify an arbitrary SQL statement for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to execute on the Oracle database.</span></span> <span data-ttu-id="9e7fb-112">También puede especificar varios bloques de parámetros de entrada a la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-112">You can also specify multiple blocks of input parameters to the SQL statement.</span></span> <span data-ttu-id="9e7fb-113">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta la instrucción SQL una vez para cada conjunto de parámetros y devuelve el resultado como un conjunto de registros (débilmente tipada) genérico.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes the SQL statement once for each set of parameters and returns any output as a generic (weakly-typed) record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e7fb-114">Puede pasar en y en los parámetros OUT procedimientos, funciones y paquetes en la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-114">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="9e7fb-115">El artefacto invocado se ejecutará con los parámetros proporcionados en la base de datos de Oracle; Sin embargo, la operación SQLEXECUTE devuelve el valor de salida y los parámetros en espera para el cliente.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-115">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="9e7fb-116">Si desea invocar procedimientos, funciones o paquetes, Microsoft recomienda que lo hace mediante la invocación de las operaciones dedicadas que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-116">If you want to invoke procedures, functions, or packages, Microsoft recommends that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="9e7fb-117">El siguiente XML muestra la estructura de la operación SQLEXECUTE:</span><span class="sxs-lookup"><span data-stu-id="9e7fb-117">The following XML shows the structure of the SQLEXECUTE operation:</span></span>  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="9e7fb-118">[Instrucción] = la instrucción SQL que se ejecuta; Por ejemplo, "Seleccione * de emp WHERE empno =: emp_no".</span><span class="sxs-lookup"><span data-stu-id="9e7fb-118">[STATEMENT] = The SQL statement to execute; for example, "SELECT * from emp WHERE empno=:emp_no".</span></span>  
  
 <span data-ttu-id="9e7fb-119">[PARAM_SPEC] = la lista de los parámetros IN en la instrucción SQL y sus tipos de datos; Por ejemplo, "emp_no número".</span><span class="sxs-lookup"><span data-stu-id="9e7fb-119">[PARAM_SPEC] = The list of the IN parameters in the SQL statement and their data types; for example, "emp_no NUMBER".</span></span>  
  
 <span data-ttu-id="9e7fb-120">[PARAM_VAL_1] = el valor del primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-120">[PARAM_VAL_1] = The value of the first parameter.</span></span>  
  
 <span data-ttu-id="9e7fb-121">Cada \<PARAMETERDATA\> sección contiene un conjunto completo de \<parámetro\> elementos que coinciden con el esquema en el \<PARAMETERSCHEMA\> sección.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-121">Each \<PARAMETERDATA\> section contains a complete set of \<PARAMETER\> elements that match the schema in the \<PARAMETERSCHEMA\> section.</span></span> <span data-ttu-id="9e7fb-122">El \<PARAMETERSET\> puede contener varios \<PARAMETERDATA\> secciones.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-122">The \<PARAMETERSET\> can contain multiple \<PARAMETERDATA\> sections.</span></span> <span data-ttu-id="9e7fb-123">Si este es el caso, la instrucción SQL se ejecuta varias veces, una vez en cada conjunto de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9e7fb-123">If this is the case, the SQL statement is executed multiple times, once against each parameter set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7fb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e7fb-124">See Also</span></span>  
 [<span data-ttu-id="9e7fb-125">Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="9e7fb-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)