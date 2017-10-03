---
title: Acceso a datos en el motor de reglas de negocios | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, data access
- Business Rules Engine, helper classes
- data, data access
ms.assetid: 38da32af-1e0d-43fb-b946-fb49a11f1681
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58de70c2befd13f4995ebd073ebd70a2e7d84ea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-access-in-the-business-rule-engine"></a><span data-ttu-id="2f245-102">Acceso a datos en el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="2f245-102">Data Access in the Business Rule Engine</span></span>
<span data-ttu-id="2f245-103">El motor de reglas admite solo objetos .NET de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="2f245-103">The rule engine supports only .NET objects natively.</span></span> <span data-ttu-id="2f245-104">Para controlar datos de una base de datos, puede utilizar directamente los objetos ADO.NET pero el motor proporciona algunas clases auxiliares para simplificar el uso de datos de bases de datos de reglas.</span><span class="sxs-lookup"><span data-stu-id="2f245-104">To handle data from a database, you can use the ADO.NET objects directly, but the engine provides some helper classes to simplify the use of database data from rules.</span></span> <span data-ttu-id="2f245-105">El motor de reglas amplía su compatibilidad exponiendo tres tipos relacionados con la base de datos: **TypedDataRow**, **TypedDataTable**, y **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="2f245-105">The rule engine extends its support by exposing three database-related types: **TypedDataRow**, **TypedDataTable**, and **DataConnection**.</span></span> <span data-ttu-id="2f245-106">En esta sección se describen estas clases auxiliares, se proporcionan recomendaciones sobre cuándo utilizar cada tipo y se analizan algunas implicaciones de rendimiento a la hora de utilizarlas.</span><span class="sxs-lookup"><span data-stu-id="2f245-106">This section describes these helper classes, gives recommendations about when to use each type, and discusses some performance implications when using them.</span></span>  
  
 <span data-ttu-id="2f245-107">Las clases auxiliares son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f245-107">The helper classes are as follows:</span></span>  
  
-   <span data-ttu-id="2f245-108">**TypedDataRow.**</span><span class="sxs-lookup"><span data-stu-id="2f245-108">**TypedDataRow.**</span></span> <span data-ttu-id="2f245-109">Construido mediante una referencia a un ADO.NET **DataRow** instancia.</span><span class="sxs-lookup"><span data-stu-id="2f245-109">Constructed by using a reference to an ADO.NET **DataRow** instance.</span></span> <span data-ttu-id="2f245-110">El **TypedDataRow** es una opción clara para reglas que solo tratan con datos de uno o un número pequeño de filas de una tabla determinada.</span><span class="sxs-lookup"><span data-stu-id="2f245-110">The **TypedDataRow** is an obvious choice for rules that only deal with data from one or a small number of rows from a particular table.</span></span>  
  
-   <span data-ttu-id="2f245-111">**TypedDataTable.**</span><span class="sxs-lookup"><span data-stu-id="2f245-111">**TypedDataTable.**</span></span> <span data-ttu-id="2f245-112">Literalmente una colección de **TypedDataRow** objetos.</span><span class="sxs-lookup"><span data-stu-id="2f245-112">Literally a collection of **TypedDataRow** objects.</span></span> <span data-ttu-id="2f245-113">Cada fila de la tabla de base de datos se ajustará como un **TypedDataRow** y se imponen en la memoria de trabajo por el motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2f245-113">Each row in the database table will be wrapped as a **TypedDataRow** and asserted into the working memory by the rule engine.</span></span>  
  
     <span data-ttu-id="2f245-114">A **TypedDataTable** requiere un ADO.NET en memoria **DataTable**, lo que puede ser un determinado de sobrecarga si este rendimiento **DataTable** contiene un gran número de filas.</span><span class="sxs-lookup"><span data-stu-id="2f245-114">A **TypedDataTable** requires an in-memory ADO.NET **DataTable**, which can be a performance overhead if this particular **DataTable** contains a very large number of rows.</span></span> <span data-ttu-id="2f245-115">Si un número reducido de filas de la tabla de base de datos es relevante y puede determinar estas filas antes de llamar a las reglas, use un **DataTable**, de lo contrario utilice **TypedDataRow**. La suposición es que un gran número de filas de la tabla de datos está relacionado con las reglas.</span><span class="sxs-lookup"><span data-stu-id="2f245-115">If a small number of rows in the database table is relevant and you can determine these rows prior to calling the rules, use a **DataTable**, otherwise use **TypedDataRow**.The assumption is that a high number of rows in the DataTable are relevant to the rules.</span></span>  
  
-   <span data-ttu-id="2f245-116">**DataConnection.**</span><span class="sxs-lookup"><span data-stu-id="2f245-116">**DataConnection.**</span></span> <span data-ttu-id="2f245-117">Representa una tabla de una base de datos a la que se ha obtenido acceso mediante una conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f245-117">Represents a table in a database accessed through a database connection.</span></span> <span data-ttu-id="2f245-118">La diferencia entre **DataConnection** y **TypedDataTable** es que además del nombre de conjunto de datos y el nombre de la tabla, **DataConnection** requiere una base de datos puede usar conexión y, opcionalmente, un contexto de transacción de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f245-118">The difference between **DataConnection** and **TypedDataTable** is that in addition to the dataset name and table name, **DataConnection** requires a usable database connection and optionally a database transaction context.</span></span>  
  
     <span data-ttu-id="2f245-119">Algunos o todos los predicados que se utilizan en las reglas con el **DataConnection** pasaría a formar parte de las restricciones de consulta en la conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f245-119">Some or all predicates used in rules with the **DataConnection** will become part of query constraints against the database connection.</span></span> <span data-ttu-id="2f245-120">solo las filas que cumplen las restricciones de consulta se recuperarán de la base de datos y serán utilizadas por el motor.</span><span class="sxs-lookup"><span data-stu-id="2f245-120">Only rows that satisfy the query constraints will be retrieved from the database and used by the engine.</span></span> <span data-ttu-id="2f245-121">Este mecanismo proporciona mejor rendimiento y consume menos memoria que mantiene un gran **DataTable** en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2f245-121">This mechanism provides better performance and consumes less memory than holding a very large **DataTable** in memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f245-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2f245-122">In This Section</span></span>  
  
-   [<span data-ttu-id="2f245-123">Consideraciones al utilizar DataConnection</span><span class="sxs-lookup"><span data-stu-id="2f245-123">Considerations When Using DataConnection</span></span>](../core/considerations-when-using-dataconnection.md)  
  
-   [<span data-ttu-id="2f245-124">Utilizar DataConnection y TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="2f245-124">Using DataConnection and TypedDataTable</span></span>](../core/using-dataconnection-and-typeddatatable.md)