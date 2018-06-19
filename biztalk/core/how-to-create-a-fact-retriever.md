---
title: Cómo crear un administrador de almacenes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IFactRetriever interface
- Business Rules Framework, bindings
- factsHandleIn object
- Business Rules Framework, code samples
- Business Rules Framework, fact retrievers
- UpdateFacts method
- Business Rules Framework, programming
ms.assetid: 503dc769-3ada-4099-a5fe-4dd03d995600
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ea60356580ae7d5a6ac2be3336ec07314211f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250212"
---
# <a name="how-to-create-a-fact-retriever"></a><span data-ttu-id="d16b8-102">Cómo crear un administrador de almacenes de datos</span><span class="sxs-lookup"><span data-stu-id="d16b8-102">How to Create a Fact Retriever</span></span>
<span data-ttu-id="d16b8-103">Un administrador de almacenes de datos es un componente que se utiliza para imponer instancias de hechos a largo plazo en una directiva durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="d16b8-103">A fact retriever is a component that is used to assert instances of long-term facts into a policy during its execution.</span></span> <span data-ttu-id="d16b8-104">Puede implementar la **IFactRetriever** interfaz y configurar una versión de directiva para utilizar esta implementación en tiempo de ejecución para que aparezcan las instancias de hechos a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="d16b8-104">You can implement the **IFactRetriever** interface and configure a policy version to use this implementation at run time to bring in the long-term fact instances.</span></span> <span data-ttu-id="d16b8-105">La versión de directiva, se invoca el **UpdateFacts** método de la implementación de almacenes de datos de hechos en cada ciclo de ejecución, si un administrador de almacenes se configura para una versión concreta.</span><span class="sxs-lookup"><span data-stu-id="d16b8-105">The policy version invokes the **UpdateFacts** method of the fact retriever implementation on every execution cycle, if a fact retriever is configured for that particular version.</span></span>  
  
 <span data-ttu-id="d16b8-106">También puede implementar la **IFactRemover** interfaz en un componente recuperador de datos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-106">You can optionally implement the **IFactRemover** interface on a fact retriever component.</span></span> <span data-ttu-id="d16b8-107">El motor de reglas, se invoca el **UpdateFactsAfterExecution** método de la **IFactRemover** cuando se elimina la directiva de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d16b8-107">The rule engine invokes the **UpdateFactsAfterExecution** method of the **IFactRemover** interface when the policy is disposed.</span></span> <span data-ttu-id="d16b8-108">Esto le ofrece la oportunidad de realizar cualquier trabajo posterior a la ejecución, como confirmar cambios en la base de datos o retirar instancias de objetos de la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="d16b8-108">This provides an opportunity to you to do any post-execution work such as committing any database changes or retracting any object instances from the rule engine's working memory.</span></span>  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a><span data-ttu-id="d16b8-109">Para especificar un administrador de almacenes de datos para una directiva</span><span class="sxs-lookup"><span data-stu-id="d16b8-109">To specify a fact retriever for a policy</span></span>  
 <span data-ttu-id="d16b8-110">Puede utilizar el siguiente código para configurar la regla establecida para utilizar una clase denominada "Retriever" en el ensamblado denominado "MyAssembly" como el administrador de almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-110">You could use the following code to configure the rule set to use a class named "Retriever" in the assembly named "MyAssembly" as the fact retriever.</span></span>  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  <span data-ttu-id="d16b8-111">Si especifica un nombre de ensamblado simple como MyAssembly como el primer parámetro para el constructor RuleEngineComponentConfiguration, el motor de reglas de BizTalk supone que es un ensamblado privado y busca el ensamblado en su carpeta de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d16b8-111">If you specify simple assembly name such as MyAssembly as the first parameter for RuleEngineComponentConfiguration constructor, the BizTalk rule engine assumes that it is a private assembly and looks for the assembly in your application folder.</span></span> <span data-ttu-id="d16b8-112">Si especifica el nombre de ensamblado completo como **MyAssembly, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = a310908b42c024fe**, el motor de reglas se da por supuesto que es un ensamblado compartido y busca el ensamblado en la información global caché de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="d16b8-112">If you specify fully qualified assembly name such as **MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=a310908b42c024fe**, the rule engine assumes that it is a shared assembly and looks for the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="d16b8-113">Puede buscar las definiciones de nombres de ensamblado simple y completo en [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span><span class="sxs-lookup"><span data-stu-id="d16b8-113">You can find the definitions of simple and fully qualified assembly names at [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span></span>  
  
 <span data-ttu-id="d16b8-114">Puede diseñar el administrador de almacenes de datos con la lógica específica de la aplicación requerida para conectar con los orígenes de datos necesarios, imponer los datos como hechos a largo plazo en el motor y especificar la lógica para actualizar o imponer nuevas instancias de los hechos a largo plazo en el motor.</span><span class="sxs-lookup"><span data-stu-id="d16b8-114">You can design the fact retriever with the required application-specific logic to connect to the required data sources, assert the data as long-term facts into the engine, and specify the logic for refreshing or asserting new instances of the long-term facts into the engine.</span></span> <span data-ttu-id="d16b8-115">Hasta que no estén actualizados, los valores que se imponen inicialmente en el motor y, por consiguiente, se guardan en caché, se utilizarán en ciclos de ejecución posteriores.</span><span class="sxs-lookup"><span data-stu-id="d16b8-115">Until updated, the values that are initially asserted into the engine and consequently cached will be used on subsequent execution cycles.</span></span> <span data-ttu-id="d16b8-116">Devuelve un objeto que es análogo a un símbolo (token) de la implementación de almacenes de datos de hechos y puede utilizarse junto con la **factsHandleIn** objeto para determinar si deben actualizarse los hechos existentes o imponer nuevos hechos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-116">The fact retriever implementation returns an object that is analogous to a token and can be used along with the **factsHandleIn** object to determine whether to update existing facts or assert new facts.</span></span> <span data-ttu-id="d16b8-117">Cuando una versión de directiva llama a sus almacenes de datos por primera vez, el **factsHandleIn** objeto siempre es null y, a continuación, toma el valor del objeto devuelto después de la ejecución de almacenes.</span><span class="sxs-lookup"><span data-stu-id="d16b8-117">When a policy version calls its fact retriever for the first time, the **factsHandleIn** object is always null and then takes the value of the return object after the fact retriever's execution.</span></span>  
  
 <span data-ttu-id="d16b8-118">Observe que para la misma instancia de motor de reglas, un hecho a largo plazo solo necesita imponerse una vez.</span><span class="sxs-lookup"><span data-stu-id="d16b8-118">Note that for the same rule engine instance, a long-term fact only needs to be asserted once.</span></span> <span data-ttu-id="d16b8-119">Por ejemplo, cuando usa el **reglas de llamada** forma de una orquestación, la instancia de directiva se mueve a una caché interna.</span><span class="sxs-lookup"><span data-stu-id="d16b8-119">For example, when you use the **Call Rules** shape in an orchestration, the policy instance is moved into an internal cache.</span></span> <span data-ttu-id="d16b8-120">En ese momento, todos los hechos a corto plazo se retraen y los hechos a largo plazo se mantienen.</span><span class="sxs-lookup"><span data-stu-id="d16b8-120">At this time, all short-term facts are retracted and long-term facts are kept.</span></span> <span data-ttu-id="d16b8-121">Si vuelve a llamarse a la misma directiva, ya sea mediante la misma instancia de orquestación o mediante una diferente del mismo host, esa instancia de directiva se recupera de la caché y vuelve a utilizarse.</span><span class="sxs-lookup"><span data-stu-id="d16b8-121">If the same policy is called again, either by the same orchestration instance or by a different orchestration instance in the same host, this policy instance is fetched from the cache and reused.</span></span> <span data-ttu-id="d16b8-122">En algunos escenarios de proceso por lotes, pueden crearse varias instancias de la misma directiva.</span><span class="sxs-lookup"><span data-stu-id="d16b8-122">In some batch processing scenarios, several policy instances of the same policy could be created.</span></span> <span data-ttu-id="d16b8-123">Si se crea una nueva instancia de directiva, debe asegurarse de que se han impuesto los hechos a largo plazo correctos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-123">If a new policy instance is created, you must ensure that the correct long-term facts are asserted.</span></span>  
  
 <span data-ttu-id="d16b8-124">Además, quizá necesite escribir código personalizado para implementar las siguientes estrategias:</span><span class="sxs-lookup"><span data-stu-id="d16b8-124">Additionally, you would need to write custom code to implement the following strategies:</span></span>  
  
-   <span data-ttu-id="d16b8-125">Saber cuándo actualizar los hechos a largo plazo</span><span class="sxs-lookup"><span data-stu-id="d16b8-125">Know when to update the long-term facts</span></span>  
  
-   <span data-ttu-id="d16b8-126">Realizar un seguimiento para saber qué instancia de motor de reglas utiliza qué hechos a largo plazo</span><span class="sxs-lookup"><span data-stu-id="d16b8-126">Keep track of which rule engine instance uses which long-term facts</span></span>  
  
 <span data-ttu-id="d16b8-127">En el siguiente código de ejemplo se muestran diversas implementaciones de administrador de almacenes de datos, que están asociadas con MyPolicy para imponer MyTableInstance como un hecho a largo plazo, mediante tipos de enlace diferentes.</span><span class="sxs-lookup"><span data-stu-id="d16b8-127">The following sample code shows different fact retriever implementations, which are associated with MyPolicy to assert MyTableInstance as a long-term fact, using different binding types.</span></span>  
  
## <a name="datatable-binding"></a><span data-ttu-id="d16b8-128">Enlace DataTable</span><span class="sxs-lookup"><span data-stu-id="d16b8-128">DataTable binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
            engine.Assert(tdt);  
            factsHandleOut = tdt;  
         }  
  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="datarow-binding"></a><span data-ttu-id="d16b8-129">Enlace DataRow</span><span class="sxs-lookup"><span data-stu-id="d16b8-129">DataRow binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
  
            // binding to the first row of CustInfo table  
            TypedDataRow tdr = new TypedDataRow(ds.Tables["CustInfo"].Rows[0],tdt);  
            engine.Assert(tdr);  
            factsHandleOut = tdr;     
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }   
}  
```  
  
 <span data-ttu-id="d16b8-130">En el siguiente código de ejemplo se muestra cómo imponer hechos .NET y XML en una implementación de administrador de almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-130">The following sample code demonstrates how to assert .NET and XML facts in a fact retriever implementation.</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
         {  
            //create .NET object instances  
            bookInstance = new Book();  
            magazineInstance = new Magazine();              
  
            //create an instance of the XML object  
            XmlDocument xd = new XmlDocument();  
  
            //load the document  
            xd.Load(@"..\myXMLInstance.xml");  
  
            //create and instantiate an instance of TXD  
            TypedXmlDocument doc = new TypedXmlDocument("mySchema",xd1);  
  
            engine.Assert(bookInstance);  
            engine.Assert(magazineInstance);  
            engine.Assert(doc);  
            factsHandleOut = doc;  
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="dataconnection-binding"></a><span data-ttu-id="d16b8-131">Enlace DataConnection</span><span class="sxs-lookup"><span data-stu-id="d16b8-131">DataConnection Binding</span></span>  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
  
         {   
            string strCmd = "Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;";  
            SqlConnection conn = new SqlConnection(strCmd);  
            DataConnection dc = new DataConnection("Northwind", "CustInfo", conn);  
  
            engine.Assert(dc);  
            factsHandleOut = dc;           
         }  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
 <span data-ttu-id="d16b8-132">Tenga en cuenta que **DataConnection**s debería imponerse siempre, cuando provenga de un administrador de almacenes, como se muestra en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="d16b8-132">Note that **DataConnection**s should always be reasserted, when provided from a fact retriever, as shown in the preceding code sample.</span></span> <span data-ttu-id="d16b8-133">La instancia del motor utiliza el **DataConnection** consultar la base de datos según las condiciones de regla y las filas devueltas por la consulta se impondrá en la memoria de trabajo del motor como **TypedDataRow**s.</span><span class="sxs-lookup"><span data-stu-id="d16b8-133">The engine instance uses the **DataConnection** to query the database based on the rule conditions, and any rows returned by the query would be asserted into the engine's working memory as **TypedDataRow**s.</span></span> <span data-ttu-id="d16b8-134">Reasserting DataConnection garantiza que las filas de una ejecución anterior del motor se borran de la memoria.</span><span class="sxs-lookup"><span data-stu-id="d16b8-134">Reasserting the DataConnection ensures that rows from a previous execution of the engine are cleared from memory.</span></span>  
  
 <span data-ttu-id="d16b8-135">De hecho, hay muy pocas ventajas imponer un **DataConnection** a través de un hecho de almacenes de datos excepto en que proporciona una manera de Exteriorizar el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d16b8-135">In fact, there is little advantage to asserting a **DataConnection** through a fact retriever except that it provides a way to externalize the data source.</span></span>