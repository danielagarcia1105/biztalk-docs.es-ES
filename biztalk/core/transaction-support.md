---
title: Compatibilidad con transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DataConnection object
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 84faac2f-6229-4692-9d1a-bf62d87d69bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc4141e248047b3add5bae6259f1039b75a40bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969093"
---
# <a name="transaction-support"></a>Compatibilidad con transacciones
Por lo general, el motor de reglas no admite transacciones. Sin embargo, puede actualizar una base de datos de forma transaccional mediante el **DataConnection** objeto tal como se muestra en los pasos siguientes:  
  
1. Crear un **SqlConnection** de objetos mediante el uso de una cadena de conexión y abre la conexión.  
  
   ```  
   SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
   connection.Open();  
   ```  
  
2. Crear un **SqlTransaction** objeto mediante una llamada a la **BeginTransaction** método en el objeto de conexión que creó en el paso 1.  
  
   ```  
   SqlTransaction transaction = connection.BeginTransaction();  
   ```  
  
3. Crear un **DataConnection** objeto mediante el uso de los objetos de conexión y transacción que creó en los pasos 1 y 2.  
  
   ```  
   DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
   ```  
  
4. Pase el **DataConnection** objeto como un hecho junto con el resto de hechos que desea pasar a la directiva y ejecutar la directiva.  
  
   ```  
   //Passing a .NET object as a fact along with the data connection  
   MyClass obj = new MyClass();  
   object[] facts = new object[2];  
   facts[0] = dc;  
   facts[1] = obj;  
   Policy pol = new Policy(policyName);  
   policy.Execute(facts);    
   ```  
  
5. Invocar el **actualización** método en el objeto de conexión de datos. Todas las actualizaciones realizadas durante la ejecución de la directiva solo se efectúan en la memoria. Debe llamar a la **actualizar** método en el objeto de conexión de datos para actualizar la base de datos.  
  
   ```  
   dc.Update();  
   ```  
  
6. Ahora, invocar **confirmar** o **reversión** en el objeto de conexión de datos según su propia lógica.  
  
   ```  
   //Checking the value of PropertyA in .net object   
   //to decide whether to commit or rollback  
   if (obj.PropertyA == true)  
   transaction.Commit();  
   else  
   transaction.Rollback();  
  
   ```  
  
7. Cierre la conexión y elimine el objeto de directiva.  
  
   ```  
   sqlCon.Close();  
   policy.Dispose();  
   ```  
  
   El siguiente código es el código completo con todos los pasos:  
  
```  
SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
connection.Open();  
SqlTransaction transaction = connection.BeginTransaction();  
DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
MyClass obj = new MyClass();  
object[] facts = new object[2];  
facts[0] = dc;  
facts[1] = obj;  
Policy pol = new Policy(policyName);  
policy.Execute(facts);    
dc.Update();  
if (obj.PropertyA == true)  
transaction.Commit();  
else  
transaction.Rollback();  
sqlCon.Close();  
policy.Dispose();  
```  
  
## <a name="comments"></a>Comentarios  
  
-   También puede usar el **OleDbConnection** y **OleDbTransaction** objetos en lugar de usar el **SqlConnection** y **SqlTransaction** objetos que se va a realizar las actualizaciones de la base de datos de forma transaccional.  
  
-   Todas las modificaciones realizadas a partir de la directiva se efectúan en la memoria. Se debe invocar el **actualizar** método en el **DataConnection** objeto para actualizar la base de datos.  
  
-   Puede confirmar o revertir la transacción mediante la invocación del **confirmación** o **reversión** método de la **DataConnection** objetos respectivamente.