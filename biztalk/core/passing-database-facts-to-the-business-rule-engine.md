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
# <a name="passing-database-facts-to-the-business-rule-engine"></a>Pasar hechos de la base de datos al motor de reglas de negocios
Cuando utiliza la herramienta de Compositor de reglas de negocio para probar una directiva que requiere un objeto DataConnection y TypedDataTable como un hecho, un objeto DataConnection y TypedDataTable se crea automáticamente y se impone en la memoria de trabajo del motor de reglas de negocios. Además, cualquier actualización de la base de datos realizada por la directiva se confirma automáticamente.  
  
 En cambio, cuando se invoca la directiva desde una orquestación, ya sea mediante el uso de la forma reglas de llamada o mediante programación, el objeto DataConnection y TypedDataTable no se crea automáticamente y las actualizaciones de base de datos no se confirman automáticamente. En este caso, debe crear un objeto DataConnection y TypedDataTable, páselo como un hecho al motor de reglas y confirmar los cambios de la base de datos mediante programación utilizando uno de los métodos siguientes.  
  
## <a name="passing-a-dataconnection-object-from-an-orchestration"></a>Pasar un objeto DataConnection desde una orquestación  
 El siguiente código de ejemplo muestra cómo crear un objeto DataConnection en la orquestación, configurar la forma Reglas de llamada para pasar el objeto DataConnection como parámetro y confirmar las actualizaciones de la base de datos después de ejecutar la directiva.  
  
1.  Cree las variables siguientes mediante la pestaña Vista orquestación con la orquestación abierta en el Diseñador de orquestaciones.  
  
    ```  
    DataCon of type Microsoft.RuleEngine.DataConnection   
    SqlCon of type System.Data.SqlClient.SqlConnection   
    SqlTran of type System.Data.SqlClient.SqlTransaction   
    ```  
  
2.  En una forma expresión antes de la forma reglas de llamada, cree un objeto DataConnection. En el ejemplo de código siguiente se muestra cómo crear un objeto DataConnection.  
  
    ```  
    SqlCon.ConnectionString = "Data Source=(local);Initial Catalog=Test;Integrated Security=SSPI";   
    SqlCon.Open();   
    SqlTran = SqlCon.BeginTransaction();   
    DataCon = new Microsoft.RuleEngine.DataConnection("test", "FlagTable", SqlCon, SqlTran);    
    ```  
  
3.  Configure la forma Reglas de llamada para pasar la variable DataCon como parámetro. Para obtener más información, consulte [cómo usar la forma reglas de llamar a](../core/how-to-use-the-call-rules-shape.md).  
  
4.  En una forma Expresión después de la forma Reglas de llamada, confirme los cambios de la base de datos realizados por la directiva. El siguiente ejemplo de código muestra cómo confirmar los cambios de la base de datos realizados por la directiva.  
  
    ```  
    DataCon.Update();   
    SqlTran.Commit();  
    ```  
  
> [!NOTE]
>  Debe usar un [SqlTransaction](http://msdn.microsoft.com/library/system.data.sqlclient.sqltransaction.aspx) objeto solo si la directiva de actualizaciones de la base de datos.  
  
## <a name="passing-a-dataconnection-object-from-a-fact-retriever"></a>Pasar un objeto DataConnection desde un administrador de almacenes de datos  
 A continuación se proporcionan los pasos habituales que hay que implementar para pasar un objeto DataConnection desde un componente administrador de almacenes de datos.  
  
1.  Cree un componente administrador de almacenes de datos que cree e imponga un objeto DataConnection en la memoria de trabajo del motor de reglas. Para obtener más información sobre cómo crear un componente recuperador de datos, vea [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).  
  
2.  Implemente el [IFactRemover](http://msdn.microsoft.com/library/Microsoft.RuleEngine.IFactRemover.aspx) de interfaz de componente recuperador de datos y confirmar los cambios de base de datos de la [UpdateFactsAfterExecution](http://msdn.microsoft.com/library/microsoft.ruleengine.ifactremover.updatefactsafterexecution.aspx) método. El motor de reglas llama a este método cuando ha terminado de ejecutar la directiva.  
  
3.  Configure la directiva para usar el componente administrador de almacenes de datos mediante la herramienta Compositor de reglas de negocio. Para obtener más información, consulte [cómo configurar un administrador de almacenes de una directiva](../core/how-to-configure-a-fact-retriever-for-a-policy.md).  
  
## <a name="see-also"></a>Vea también  
 [Acceso a datos en el motor de reglas de negocios](../core/data-access-in-the-business-rule-engine.md)   
 [Cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md)   
 [Cómo configurar un administrador de almacenes de una directiva](../core/how-to-configure-a-fact-retriever-for-a-policy.md)