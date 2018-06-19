---
title: Pasar hechos de base de datos para el motor de reglas de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62285bbe-ee64-4c26-b48e-55f666dc1304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ae35802263b71965698e0bb56d1ddbee9ae0a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264140"
---
# <a name="passing-database-facts-to-the-business-rule-engine"></a><span data-ttu-id="4802e-102">Pasar hechos de la base de datos al motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="4802e-102">Passing Database Facts to the Business Rule Engine</span></span>
<span data-ttu-id="4802e-103">Cuando utiliza la herramienta de Compositor de reglas de negocio para probar una directiva que requiere un objeto DataConnection y TypedDataTable como un hecho, un objeto DataConnection y TypedDataTable se crea automáticamente y se impone en la memoria de trabajo del motor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="4802e-103">When you use the Business Rule Composer tool to test a policy that requires a DataConnection/TypedDataTable object as a fact, a DataConnection/TypedDataTable object is automatically created for you and asserted into the Business Rule Engine's working memory.</span></span> <span data-ttu-id="4802e-104">Además, cualquier actualización de la base de datos realizada por la directiva se confirma automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4802e-104">Additionally, any database updates by the policy are committed automatically.</span></span>  
  
 <span data-ttu-id="4802e-105">En cambio, cuando se invoca la directiva desde una orquestación, ya sea mediante el uso de la forma reglas de llamada o mediante programación, el objeto DataConnection y TypedDataTable no se crea automáticamente y las actualizaciones de base de datos no se confirman automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4802e-105">In contrast, when you invoke the policy from an orchestration, either by using the Call Rules shape or programmatically, the DataConnection/TypedDataTable object is not created for you and the database updates are not committed automatically.</span></span> <span data-ttu-id="4802e-106">En este caso, debe crear un objeto DataConnection y TypedDataTable, páselo como un hecho al motor de reglas y confirmar los cambios de la base de datos mediante programación utilizando uno de los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4802e-106">In this case, you should create a DataConnection/TypedDataTable object, pass it as a fact to the rule engine, and commit the database changes programmatically by using one of the following methods.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a><span data-ttu-id="4802e-107">Pasar un objeto DataConnection desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="4802e-107">Passing a DataConnection Object from an Orchestration</span></span>  
 <span data-ttu-id="4802e-108">El siguiente código de ejemplo muestra cómo crear un objeto DataConnection en la orquestación, configurar la forma Reglas de llamada para pasar el objeto DataConnection como parámetro y confirmar las actualizaciones de la base de datos después de ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="4802e-108">The following sample code demonstrates how to create a DataConnection object in the orchestration, configure the Call Rules shape to pass the DataConnection object as a parameter, and commit any database updates after the policy is executed.</span></span>  
  
1.  <span data-ttu-id="4802e-109">Cree las variables siguientes mediante la pestaña Vista orquestación con la orquestación abierta en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="4802e-109">Create the following variables using the Orchestration View tab with the orchestration open in the Orchestration Designer.</span></span>  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  <span data-ttu-id="4802e-110">En una forma expresión antes de la forma reglas de llamada, cree un objeto DataConnection.</span><span class="sxs-lookup"><span data-stu-id="4802e-110">In an Expression shape before the Call Rules shape, create a DataConnection object.</span></span> <span data-ttu-id="4802e-111">En el ejemplo de código siguiente se muestra cómo crear un objeto DataConnection.</span><span class="sxs-lookup"><span data-stu-id="4802e-111">The following code example demonstrates how to create a DataConnection object.</span></span>  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  <span data-ttu-id="4802e-112">Configure la forma Reglas de llamada para pasar la variable DataCon como parámetro.</span><span class="sxs-lookup"><span data-stu-id="4802e-112">Configure the Call Rules shape to pass the DataCon variable as a parameter.</span></span> <span data-ttu-id="4802e-113">Para obtener más información, consulte [cómo usar la forma reglas de llamar a](../core/how-to-use-the-call-rules-shape.md).</span><span class="sxs-lookup"><span data-stu-id="4802e-113">For more information, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
4.  <span data-ttu-id="4802e-114">En una forma Expresión después de la forma Reglas de llamada, confirme los cambios de la base de datos realizados por la directiva.</span><span class="sxs-lookup"><span data-stu-id="4802e-114">In an Expression shape after the Call Rules shape, commit the database changes made by the policy.</span></span> <span data-ttu-id="4802e-115">El siguiente ejemplo de código muestra cómo confirmar los cambios de la base de datos realizados por la directiva.</span><span class="sxs-lookup"><span data-stu-id="4802e-115">The following code example demonstrates how to commit the database changes made by the policy.</span></span>  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="4802e-116">Debe usar un [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) objeto solo si la directiva de actualizaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4802e-116">You need to use a [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) object only if the policy updates the database.</span></span>  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a><span data-ttu-id="4802e-117">Pasar un objeto DataConnection desde un administrador de almacenes de datos</span><span class="sxs-lookup"><span data-stu-id="4802e-117">Passing a DataConnection Object from a Fact Retriever</span></span>  
 <span data-ttu-id="4802e-118">A continuación se proporcionan los pasos habituales que hay que implementar para pasar un objeto DataConnection desde un componente administrador de almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="4802e-118">Here are the typical steps you need to implement to pass a DataConnection object from a fact retriever component.</span></span>  
  
1.  <span data-ttu-id="4802e-119">Cree un componente administrador de almacenes de datos que cree e imponga un objeto DataConnection en la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="4802e-119">Create a fact retriever component that creates and asserts a DataConnection object into the rule engine's working memory.</span></span> <span data-ttu-id="4802e-120">Para obtener más información sobre cómo crear un componente recuperador de datos, vea [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).</span><span class="sxs-lookup"><span data-stu-id="4802e-120">For more information about how to create a fact retriever component, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
2.  <span data-ttu-id="4802e-121">Implemente el [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) de interfaz de componente recuperador de datos y confirmar los cambios de base de datos de la [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) método.</span><span class="sxs-lookup"><span data-stu-id="4802e-121">Implement the [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) interface on fact retriever component, and commit the database changes from the [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) method.</span></span> <span data-ttu-id="4802e-122">El motor de reglas llama a este método cuando ha terminado de ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="4802e-122">This method is called by the rule engine after it is done with executing the policy.</span></span>  
  
3.  <span data-ttu-id="4802e-123">Configure la directiva para usar el componente administrador de almacenes de datos mediante la herramienta Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="4802e-123">Configure the policy to use the fact retriever component by using the Business Rule Composer tool.</span></span> <span data-ttu-id="4802e-124">Para obtener más información, consulte [cómo configurar un administrador de almacenes de una directiva](../core/how-to-configure-a-fact-retriever-for-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4802e-124">For more information, see [How to Configure a Fact Retriever for a Policy](../core/how-to-configure-a-fact-retriever-for-a-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4802e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4802e-125">See Also</span></span>  
 <span data-ttu-id="4802e-126">[Acceso a datos en el motor de reglas de negocios](../core/data-access-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="4802e-126">[Data Access in the Business Rule Engine](../core/data-access-in-the-business-rule-engine.md) </span></span>  
 <span data-ttu-id="4802e-127">[Cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md) </span><span class="sxs-lookup"><span data-stu-id="4802e-127">[How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md) </span></span>  
 [<span data-ttu-id="4802e-128">Cómo configurar un administrador de almacenes de una directiva</span><span class="sxs-lookup"><span data-stu-id="4802e-128">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)