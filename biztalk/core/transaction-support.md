---
title: Compatibilidad con transacciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataConnection object
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 84faac2f-6229-4692-9d1a-bf62d87d69bb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fc1d7a1edd18663cb21a85037cf3e662948fc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-support"></a><span data-ttu-id="8eee3-102">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="8eee3-102">Transaction Support</span></span>
<span data-ttu-id="8eee3-103">Por lo general, el motor de reglas no admite transacciones.</span><span class="sxs-lookup"><span data-stu-id="8eee3-103">The rule engine does not support transactions in general.</span></span> <span data-ttu-id="8eee3-104">Sin embargo, puede actualizar una base de datos de forma transaccional mediante el **DataConnection** objeto tal y como se muestra en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8eee3-104">However, you can update a database in a transactional manner by using the **DataConnection** object as shown in the following steps:</span></span>  
  
1.  <span data-ttu-id="8eee3-105">Crear un **SqlConnection** de objetos mediante el uso de una cadena de conexión y abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="8eee3-105">Create a **SqlConnection** object by using a connection string, and open the connection.</span></span>  
  
    ```  
    SqlConnection connection = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
    connection.Open();  
    ```  
  
2.  <span data-ttu-id="8eee3-106">Crear un **SqlTransaction** objeto mediante una llamada a la **BeginTransaction** método en el objeto de conexión que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8eee3-106">Create a **SqlTransaction** object by calling the **BeginTransaction** method on the connection object you created in step 1.</span></span>  
  
    ```  
    SqlTransaction transaction = connection.BeginTransaction();  
    ```  
  
3.  <span data-ttu-id="8eee3-107">Crear un **DataConnection** objeto mediante el uso de los objetos de conexión y transacción que creó en los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="8eee3-107">Create a **DataConnection** object by using the connection and transaction objects you created in steps 1 and 2.</span></span>  
  
    ```  
    DataConnection dc = new DataConnection(datasetName, tableName, connection, transaction);  
    ```  
  
4.  <span data-ttu-id="8eee3-108">Pasar el **DataConnection** objeto como un hecho junto con el resto de hechos que desea pasar a la directiva y ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="8eee3-108">Pass the **DataConnection** object as a fact along with any other facts you want to pass to the policy, and execute the policy.</span></span>  
  
    ```  
    //Passing a .NET object as a fact along with the data connection  
    MyClass obj = new MyClass();  
    object[] facts = new object[2];  
    facts[0] = dc;  
    facts[1] = obj;  
    Policy pol = new Policy(policyName);  
    policy.Execute(facts);    
    ```  
  
5.  <span data-ttu-id="8eee3-109">Invocar la **actualización** método en el objeto de conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="8eee3-109">Invoke the **Update** method on the data connection object.</span></span> <span data-ttu-id="8eee3-110">Todas las actualizaciones realizadas durante la ejecución de la directiva solo se efectúan en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8eee3-110">All the updates done while executing the policy are done only in memory.</span></span> <span data-ttu-id="8eee3-111">Debe llamar a la **actualizar** método en el objeto de conexión de datos para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8eee3-111">You must call the **Update** method on the data connection object to update the database.</span></span>  
  
    ```  
    dc.Update();  
    ```  
  
6.  <span data-ttu-id="8eee3-112">Ahora, invocar **confirmar** o **reversión** en el objeto de conexión de datos según su propia lógica.</span><span class="sxs-lookup"><span data-stu-id="8eee3-112">Now, invoke **Commit** or **Rollback** on the data connection object based on your own logic.</span></span>  
  
    ```  
    //Checking the value of PropertyA in .net object   
    //to decide whether to commit or rollback  
    if (obj.PropertyA == true)  
    transaction.Commit();  
    else  
    transaction.Rollback();  
  
    ```  
  
7.  <span data-ttu-id="8eee3-113">Cierre la conexión y elimine el objeto de directiva.</span><span class="sxs-lookup"><span data-stu-id="8eee3-113">Close the connection, and dispose the policy object.</span></span>  
  
    ```  
    sqlCon.Close();  
    policy.Dispose();  
    ```  
  
 <span data-ttu-id="8eee3-114">El siguiente código es el código completo con todos los pasos:</span><span class="sxs-lookup"><span data-stu-id="8eee3-114">The following code is the complete code with all the steps:</span></span>  
  
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
  
## <a name="comments"></a><span data-ttu-id="8eee3-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8eee3-115">Comments</span></span>  
  
-   <span data-ttu-id="8eee3-116">También puede usar el **OleDbConnection** y **OleDbTransaction** objetos en lugar de utilizar el **SqlConnection** y **SqlTransaction** objetos que se va a realizar las actualizaciones de base de datos de forma transaccional.</span><span class="sxs-lookup"><span data-stu-id="8eee3-116">You can also use the **OleDbConnection** and **OleDbTransaction** objects instead of using the **SqlConnection** and **SqlTransaction** objects to perform database updates in a transactional manner.</span></span>  
  
-   <span data-ttu-id="8eee3-117">Todas las modificaciones realizadas a partir de la directiva se efectúan en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8eee3-117">All the modifications done from the policy are done in memory.</span></span> <span data-ttu-id="8eee3-118">Se debe invocar el **actualizar** método en el **DataConnection** objeto que se va a actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8eee3-118">You must invoke the **Update** method on the **DataConnection** object to update the database.</span></span>  
  
-   <span data-ttu-id="8eee3-119">Puede confirmar o revertir la transacción mediante la invocación de la **confirmación** o **reversión** método de la **DataConnection** objetos respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8eee3-119">You can either commit or roll back the transaction by invoking the **Commit** or **Rollback** method of the **DataConnection** objects respectively.</span></span>