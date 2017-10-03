---
title: "Cómo crear un administrador de almacenes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ea60356580ae7d5a6ac2be3336ec07314211f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-fact-retriever"></a>Cómo crear un administrador de almacenes de datos
Un administrador de almacenes de datos es un componente que se utiliza para imponer instancias de hechos a largo plazo en una directiva durante su ejecución. Puede implementar la **IFactRetriever** interfaz y configurar una versión de directiva para utilizar esta implementación en tiempo de ejecución para que aparezcan las instancias de hechos a largo plazo. La versión de directiva, se invoca el **UpdateFacts** método de la implementación de almacenes de datos de hechos en cada ciclo de ejecución, si un administrador de almacenes se configura para una versión concreta.  
  
 También puede implementar la **IFactRemover** interfaz en un componente recuperador de datos. El motor de reglas, se invoca el **UpdateFactsAfterExecution** método de la **IFactRemover** cuando se elimina la directiva de la interfaz. Esto le ofrece la oportunidad de realizar cualquier trabajo posterior a la ejecución, como confirmar cambios en la base de datos o retirar instancias de objetos de la memoria de trabajo del motor de reglas.  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a>Para especificar un administrador de almacenes de datos para una directiva  
 Puede utilizar el siguiente código para configurar la regla establecida para utilizar una clase denominada "Retriever" en el ensamblado denominado "MyAssembly" como el administrador de almacenes de datos.  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  Si especifica un nombre de ensamblado simple como MyAssembly como el primer parámetro para el constructor RuleEngineComponentConfiguration, el motor de reglas de BizTalk supone que es un ensamblado privado y busca el ensamblado en su carpeta de aplicación. Si especifica el nombre de ensamblado completo como **MyAssembly, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = a310908b42c024fe**, el motor de reglas se da por supuesto que es un ensamblado compartido y busca el ensamblado en la información global caché de ensamblados (GAC). Puede buscar las definiciones de nombres de ensamblado simple y completo en [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).  
  
 Puede diseñar el administrador de almacenes de datos con la lógica específica de la aplicación requerida para conectar con los orígenes de datos necesarios, imponer los datos como hechos a largo plazo en el motor y especificar la lógica para actualizar o imponer nuevas instancias de los hechos a largo plazo en el motor. Hasta que no estén actualizados, los valores que se imponen inicialmente en el motor y, por consiguiente, se guardan en caché, se utilizarán en ciclos de ejecución posteriores. Devuelve un objeto que es análogo a un símbolo (token) de la implementación de almacenes de datos de hechos y puede utilizarse junto con la **factsHandleIn** objeto para determinar si deben actualizarse los hechos existentes o imponer nuevos hechos. Cuando una versión de directiva llama a sus almacenes de datos por primera vez, el **factsHandleIn** objeto siempre es null y, a continuación, toma el valor del objeto devuelto después de la ejecución de almacenes.  
  
 Observe que para la misma instancia de motor de reglas, un hecho a largo plazo solo necesita imponerse una vez. Por ejemplo, cuando usa el **reglas de llamada** forma de una orquestación, la instancia de directiva se mueve a una caché interna. En ese momento, todos los hechos a corto plazo se retraen y los hechos a largo plazo se mantienen. Si vuelve a llamarse a la misma directiva, ya sea mediante la misma instancia de orquestación o mediante una diferente del mismo host, esa instancia de directiva se recupera de la caché y vuelve a utilizarse. En algunos escenarios de proceso por lotes, pueden crearse varias instancias de la misma directiva. Si se crea una nueva instancia de directiva, debe asegurarse de que se han impuesto los hechos a largo plazo correctos.  
  
 Además, quizá necesite escribir código personalizado para implementar las siguientes estrategias:  
  
-   Saber cuándo actualizar los hechos a largo plazo  
  
-   Realizar un seguimiento para saber qué instancia de motor de reglas utiliza qué hechos a largo plazo  
  
 En el siguiente código de ejemplo se muestran diversas implementaciones de administrador de almacenes de datos, que están asociadas con MyPolicy para imponer MyTableInstance como un hecho a largo plazo, mediante tipos de enlace diferentes.  
  
## <a name="datatable-binding"></a>Enlace DataTable  
  
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
  
## <a name="datarow-binding"></a>Enlace DataRow  
  
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
  
 En el siguiente código de ejemplo se muestra cómo imponer hechos .NET y XML en una implementación de administrador de almacenes de datos.  
  
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
  
## <a name="dataconnection-binding"></a>Enlace DataConnection  
  
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
  
 Tenga en cuenta que **DataConnection**s debería imponerse siempre, cuando provenga de un administrador de almacenes, como se muestra en el ejemplo de código anterior. La instancia del motor utiliza el **DataConnection** consultar la base de datos según las condiciones de regla y las filas devueltas por la consulta se impondrá en la memoria de trabajo del motor como **TypedDataRow**s. Reasserting DataConnection garantiza que las filas de una ejecución anterior del motor se borran de la memoria.  
  
 De hecho, hay muy pocas ventajas imponer un **DataConnection** a través de un hecho de almacenes de datos excepto en que proporciona una manera de Exteriorizar el origen de datos.