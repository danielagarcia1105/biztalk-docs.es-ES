---
title: Utilizar DataConnection y TypedDataTable | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Assert function [Business Rules Engine], TypedData table
- Business Rules Engine, DataConnection tips
- TypedData table
- Business Rules Engine, TypedData table tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], DataConnection
ms.assetid: e825803e-6626-4ddd-a77e-75a3ba2b74a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287548"
---
# <a name="using-dataconnection-and-typeddatatable"></a><span data-ttu-id="73c34-102">Utilizar DataConnection y TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="73c34-102">Using DataConnection and TypedDataTable</span></span>
<span data-ttu-id="73c34-103">En muchos escenarios, el uso **DataConnection** proporciona un mejor rendimiento y consume menos memoria que el uso de **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="73c34-103">In many scenarios, using **DataConnection** provides better performance and consumes less memory than using **TypedDataTable**.</span></span> <span data-ttu-id="73c34-104">Sin embargo, **TypedDataTable** puede ser necesario en algunos casos debido a ciertas restricciones sobre el uso de **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="73c34-104">However, **TypedDataTable** may be required in some cases because of certain restrictions on using **DataConnection**.</span></span> <span data-ttu-id="73c34-105">En otros casos, con **TypedDataTable** , se puede obtener un mejor rendimiento que el uso de **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="73c34-105">In some other cases, using **TypedDataTable** may yield better performance than using **DataConnection**.</span></span> <span data-ttu-id="73c34-106">En este tema se describen los criterios y factores que se deben tener en cuenta para elegir el enfoque adecuado.</span><span class="sxs-lookup"><span data-stu-id="73c34-106">This topic describes the criteria and factors that you should consider for choosing the right approach.</span></span>  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a><span data-ttu-id="73c34-107">Cuándo utilizar TypedDataTable en lugar de DataConnection</span><span class="sxs-lookup"><span data-stu-id="73c34-107">When to use TypedDataTable instead of DataConnection</span></span>  
 <span data-ttu-id="73c34-108">Utilice TypedDataTable en lugar de DataConnection en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="73c34-108">Use TypedDataTable instead of DataConnection in the following instances:</span></span>  
  
-   <span data-ttu-id="73c34-109">Es necesario realizar cambios en los datos, pero la tabla no posee una clave principal.</span><span class="sxs-lookup"><span data-stu-id="73c34-109">Data changes need to be made but the table does not have a primary key.</span></span> <span data-ttu-id="73c34-110">Para realizar cambios de datos mediante el uso de **DataConnection**, se requiere una clave principal.</span><span class="sxs-lookup"><span data-stu-id="73c34-110">To make data changes by using **DataConnection**, a primary key is required.</span></span> <span data-ttu-id="73c34-111">Por lo tanto, si no hay ninguna clave principal, **TypedDataTable** es el único enfoque viable.</span><span class="sxs-lookup"><span data-stu-id="73c34-111">Therefore, if there is no primary key, **TypedDataTable** is the only viable approach.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73c34-112">El motor de reglas sólo actualiza los valores de memoria para un **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="73c34-112">The rule engine only updates the values in memory for a **TypedDataTable**.</span></span> <span data-ttu-id="73c34-113">Es el usuario que llama quien debe hacer permanentes estos cambios.</span><span class="sxs-lookup"><span data-stu-id="73c34-113">It is up to the caller to make those changes permanent.</span></span>  
  
-   <span data-ttu-id="73c34-114">La selectividad es alta, lo que significa que un alto porcentaje de filas de la tabla pasará las pruebas especificadas como condiciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="73c34-114">Selectivity is high, which means that a large percentage of rows in the table will pass the tests specified as rule conditions.</span></span> <span data-ttu-id="73c34-115">En este caso, **DataConnection** no proporciona demasiadas ventajas y puede funcionar peor que **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="73c34-115">In this case, **DataConnection** does not provide much benefit and it may perform worse than **TypedDataTable**.</span></span>  
  
-   <span data-ttu-id="73c34-116">Por regla general, se trata de una tabla pequeña que contiene menos de 500 filas.</span><span class="sxs-lookup"><span data-stu-id="73c34-116">The table is small, typically, a table that contains fewer than 500 rows.</span></span> <span data-ttu-id="73c34-117">Tenga en cuenta que este número puede variar en función de la forma de regla y de la memoria que esté disponible en el motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="73c34-117">Note that this number could be larger or smaller depending on the rule shape and the memory available to the rule engine.</span></span>  
  
-   <span data-ttu-id="73c34-118">El comportamiento del encadenamiento de reglas se encuentra en un conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="73c34-118">Rule-chaining behavior is expected in a rule set.</span></span> <span data-ttu-id="73c34-119">Llamar a la **actualización** funcionen en una **DataConnection** no es compatible, pero podría invocar **DataConnection.Update** en una regla mediante un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="73c34-119">Calling the **Update** function on a **DataConnection** is not supported, but you could invoke **DataConnection.Update** in a rule using a helper method.</span></span> <span data-ttu-id="73c34-120">Cuando se requiere, el encadenamiento de reglas **TypedDataTable** es una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="73c34-120">When rule chaining is required, **TypedDataTable** is a better choice.</span></span>  
  
-   <span data-ttu-id="73c34-121">Una o varias columnas de la tabla contienen una gran cantidad de datos que no resultan de utilidad para las reglas.</span><span class="sxs-lookup"><span data-stu-id="73c34-121">One or more columns in the table hold a very large amount of data that is not required by the rules.</span></span> <span data-ttu-id="73c34-122">Un ejemplo podría ser una base de datos de imágenes, donde las columnas contienen la imagen (una gran cantidad de datos), el nombre, la fecha, etc.</span><span class="sxs-lookup"><span data-stu-id="73c34-122">An example is an image database, where the columns hold the image (large amount of data), name, date, and so on.</span></span> <span data-ttu-id="73c34-123">Si la imagen no es necesaria, seleccione únicamente las columnas que utilizarán las reglas.</span><span class="sxs-lookup"><span data-stu-id="73c34-123">If the image is not required, it may be better to select only the columns needed by the rules.</span></span> <span data-ttu-id="73c34-124">Por ejemplo, emitir una consulta como "Seleccionar nombre y fecha en la tabla" puede ser más eficaz que el uso de **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="73c34-124">For example, issuing a query such as "SELECT Name, Date from TABLE" can be more efficient than using **DataConnection**.</span></span>  
  
-   <span data-ttu-id="73c34-125">Si muchas reglas necesitan o actualización la misma fila de la base de datos, utilizando un **TypedDataTable**, la fila se comparte entre todas las reglas, y si la condición es el mismo (por ejemplo, Table.Column == 5), se puede optimizar la evaluación de condición.</span><span class="sxs-lookup"><span data-stu-id="73c34-125">If many rules need or update the same database row, using a **TypedDataTable**, the row is shared between all rules, and if the condition is the same (for example, Table.Column == 5), the condition evaluation can be optimized.</span></span> <span data-ttu-id="73c34-126">Con un **DataConnection**, por lo general, se genera una consulta para cada regla que usa la **DataConnection**.</span><span class="sxs-lookup"><span data-stu-id="73c34-126">With a **DataConnection**, in general, a query is generated for each rule that uses the **DataConnection**.</span></span> <span data-ttu-id="73c34-127">Aunque las filas se reutilizan (si la tabla tiene una clave primaria), pueden generarse varias consultas para obtener los mismos datos cada vez.</span><span class="sxs-lookup"><span data-stu-id="73c34-127">Although the rows are reused (if the table has a primary key), multiple queries could be generated to get the same data each time.</span></span>  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a><span data-ttu-id="73c34-128">Cuándo utilizar DataConnection en lugar de TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="73c34-128">When to use DataConnection instead of TypedDataTable</span></span>  
 <span data-ttu-id="73c34-129">Utilice DataConnection en lugar de TypedDataTable en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="73c34-129">Use DataConnection instead of TypedDataTable in the following instances:</span></span>  
  
-   <span data-ttu-id="73c34-130">La tabla contiene un gran número de filas, pero la selectividad es baja, solo un pequeño porcentaje de filas cumplirán las condiciones de regla.</span><span class="sxs-lookup"><span data-stu-id="73c34-130">The table contains a large number of rows, but selectivity is low—only a small percentage of rows will satisfy the rule conditions.</span></span>  
  
-   <span data-ttu-id="73c34-131">Solo existe una tabla de base de datos grande y el resto de objetos que se utilizan en la regla poseen un número reducido de instancias.</span><span class="sxs-lookup"><span data-stu-id="73c34-131">Only one database table is large; all other objects used in the rule have a small number of instances.</span></span> <span data-ttu-id="73c34-132">En el peor de los casos, el número de consultas que se ejecutan en la base de datos coincide con la suma de todas las instancias utilizadas en la regla.</span><span class="sxs-lookup"><span data-stu-id="73c34-132">In the worst case, the number of queries executed against the database is equal to the product of all the other instances used in the rule.</span></span>  
  
-   <span data-ttu-id="73c34-133">Las reglas están formadas exclusivamente por condiciones conjuntivas y en ellas se utilizan objetos ajenos a la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="73c34-133">Rules consist exclusively of conjunctive conditions and objects other than database table are used in these rules.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c34-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c34-134">See Also</span></span>  
 [<span data-ttu-id="73c34-135">Acceso a datos en el motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="73c34-135">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)