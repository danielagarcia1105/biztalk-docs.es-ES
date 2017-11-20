---
title: "Ejecutar la operación SQLEXECUTE en base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bda1c864e7a6eff442099d6caf1a2bba98e7f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="26f0f-102">Ejecutar la operación SQLEXECUTE en base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="26f0f-102">Run SQLEXECUTE operation in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="26f0f-103">La[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto estándar de operaciones en artefactos de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="26f0f-103">The[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="26f0f-104">Mediante el uso de estas operaciones, puede hacer cosas como llamada a una función de Oracle o un procedimiento, o realizar operaciones del lenguaje (DML) de manipulación de datos de básico SQL en tablas.</span><span class="sxs-lookup"><span data-stu-id="26f0f-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="26f0f-105">Sin embargo, pueden haber escenarios controlados por la lógica de negocios que requieren realizar operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no expuesta.</span><span class="sxs-lookup"><span data-stu-id="26f0f-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="26f0f-106">Por ejemplo, puede:</span><span class="sxs-lookup"><span data-stu-id="26f0f-106">For example, you may want to:</span></span>  
  
-   <span data-ttu-id="26f0f-107">Realizar una operación en artefactos de base de datos que no se exponen a través de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtenga el CURVAL o NEXTVAL de las secuencias de Oracle.</span><span class="sxs-lookup"><span data-stu-id="26f0f-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
-   <span data-ttu-id="26f0f-108">Realizar operaciones de lenguaje de definición de datos; Por ejemplo, crear una tabla.</span><span class="sxs-lookup"><span data-stu-id="26f0f-108">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
-   <span data-ttu-id="26f0f-109">Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal que se crea mediante la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="26f0f-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
-   <span data-ttu-id="26f0f-110">Realizar operaciones más complejas de DML en tablas que las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies; por ejemplo, para realizar una consulta que incluye una cláusula de combinación.</span><span class="sxs-lookup"><span data-stu-id="26f0f-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
 <span data-ttu-id="26f0f-111">Para estos tipos de escenarios, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] emerge la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="26f0f-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="26f0f-112">Mediante la operación SQLEXECUTE, puede realizar una instrucción SQL con parámetros en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="26f0f-112">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="26f0f-113">La operación SQLEXECUTE admite un bloque de parámetro de entrada consta de los conjuntos de parámetros que permiten ejecutar la misma instrucción SQL una vez para cada conjunto.</span><span class="sxs-lookup"><span data-stu-id="26f0f-113">The SQLEXECUTE operation supports an input parameter block comprised of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="26f0f-114">La operación SQLEXECUTE devuelve los resultados de la instrucción SQL en un conjunto de registros genérico.</span><span class="sxs-lookup"><span data-stu-id="26f0f-114">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="26f0f-115">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="26f0f-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="26f0f-116">Los ejemplos de este tema se utiliza una secuencia de Oracle denominan TID_SEQ.</span><span class="sxs-lookup"><span data-stu-id="26f0f-116">The examples in this topic use an Oracle SEQUENCE named TID_SEQ.</span></span> <span data-ttu-id="26f0f-117">Una secuencia de comandos para generar esta secuencia se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="26f0f-117">A script to generate this SEQUENCE is supplied with the SDK samples.</span></span> <span data-ttu-id="26f0f-118">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="26f0f-118">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="26f0f-119">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="26f0f-119">The WCF Client Class</span></span>  
 <span data-ttu-id="26f0f-120">El modelo de servicio WCF genera un cliente WCF dedicado, **SQLEXECUTEClient**, para la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="26f0f-120">The WCF service model generates a dedicated WCF client, **SQLEXECUTEClient**, for the SQLEXECUTE operation.</span></span> <span data-ttu-id="26f0f-121">El código siguiente muestra el **SQLEXECUTEClient** y la firma del método que se llama para invocar la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="26f0f-121">The following code shows the **SQLEXECUTEClient** and the signature of the method that you call to invoke the SQLEXECUTE operation.</span></span>  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 <span data-ttu-id="26f0f-122">La operación SQLEXECUTE devuelve un conjunto de registros genérico.</span><span class="sxs-lookup"><span data-stu-id="26f0f-122">The SQLEXECUTE operation returns a generic record set.</span></span> <span data-ttu-id="26f0f-123">Este conjunto de registros contiene los valores (si existe) que se devuelven las instrucciones que se ejecuta la operación SQLEXECUTE.</span><span class="sxs-lookup"><span data-stu-id="26f0f-123">This record set contains the values (if any) that are returned by the statements that the SQLEXECUTE operation executes.</span></span> <span data-ttu-id="26f0f-124">Puede pasar conjuntos de parámetros de entrada a la operación SQLEXECUTE en una colección de objetos PARAMETERDATA, cada uno de los cuales contiene una colección de parámetros de entrada representadas como cadenas.</span><span class="sxs-lookup"><span data-stu-id="26f0f-124">You can pass sets of input parameters to the SQLEXECUTE operation in a collection of PARAMETERDATA objects, each of which contains a collection of input parameters represented as strings.</span></span> <span data-ttu-id="26f0f-125">El código siguiente muestra la definición de un conjunto PARAMETERDATA.</span><span class="sxs-lookup"><span data-stu-id="26f0f-125">The following code shows the definition of a PARAMETERDATA set.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a><span data-ttu-id="26f0f-126">Invocar la operación SQLEXECUTE</span><span class="sxs-lookup"><span data-stu-id="26f0f-126">Invoking the SQLEXECUTE Operation</span></span>  
 <span data-ttu-id="26f0f-127">Para invocar la operación SQLEXECUTE mediante un cliente WCF, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="26f0f-127">To invoke the SQLEXECUTE operation by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="26f0f-128">Generar un **SQLEXECUTEClient** clase para la tabla de destino o la vista.</span><span class="sxs-lookup"><span data-stu-id="26f0f-128">Generate a **SQLEXECUTEClient** class for the target table or view.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="26f0f-129">La operación SQLEXECUTE aparece bajo el nodo raíz (**/**) en el **seleccione una categoría de** panel en el **Agregar referencia de servicio de adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="26f0f-129">The SQLEXECUTE operation is surfaced under the root node (**/**) in the **Select a category** pane in the **Add Adapter Service Reference** dialog box.</span></span>  
  
2.  <span data-ttu-id="26f0f-130">Cree una instancia de la **SQLEXECUTEClient** clase e invocar el **SQLEXECUTE** método para ejecutar instrucciones SQL en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="26f0f-130">Create an instance of the **SQLEXECUTEClient** class, and invoke the **SQLEXECUTE** method to execute SQL statements on the Oracle database.</span></span>  
  
 <span data-ttu-id="26f0f-131">Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [información general sobre el modelo de servicio WCF con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="26f0f-131">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF service model with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="26f0f-132">En el ejemplo siguiente se usa el **SQLEXECUTEClient** para obtener el siguiente valor de una secuencia de Oracle, TID_SEQ, mediante la ejecución de la siguiente instrucción SQL: `SELECT tid_seq.nextval id from DUAL`.</span><span class="sxs-lookup"><span data-stu-id="26f0f-132">The following example uses the **SQLEXECUTEClient** to get the next value of an Oracle SEQUENCE, TID_SEQ, by executing the following SQL statement: `SELECT tid_seq.nextval id from DUAL`.</span></span> <span data-ttu-id="26f0f-133">A continuación, se escribe el resultado en la consola.</span><span class="sxs-lookup"><span data-stu-id="26f0f-133">The output is then written to the console.</span></span>  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="26f0f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="26f0f-134">See Also</span></span>  
 [<span data-ttu-id="26f0f-135">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="26f0f-135">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)