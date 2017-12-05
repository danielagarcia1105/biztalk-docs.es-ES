---
title: "Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720da748059d3fe3da376ea42495a2587577f5ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="a7b87-102">Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a7b87-102">Complete operations on tables with large data types in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="a7b87-103">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador realizar operaciones en tablas de interfaz y las vistas con tipos de datos de gran tamaño como BLOB, CLOB, NCLOB y BFILE.</span><span class="sxs-lookup"><span data-stu-id="a7b87-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform operations on interface tables and views with large data types such as BLOB, CLOB, NCLOB, and BFILE.</span></span>  
  
-   <span data-ttu-id="a7b87-104">Para las columnas de tipo BLOB, CLOB y NCLOB, el adaptador permite a los clientes leer, así como actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-104">For columns of type BLOB, CLOB, and NCLOB, the adapter enables clients to read as well as update data.</span></span> <span data-ttu-id="a7b87-105">El adaptador expone Read_\<*LOBColName* \> y Update_\<*LOBColName* \> operations para leer y actualizar datos respectivamente, donde \< *LOBColName* \> es el nombre de columna con el tipo de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a7b87-105">The adapter exposes Read_\<*LOBColName*\> and Update_\<*LOBColName*\> operations to read and update data respectively, where \<*LOBColName*\> is the name of column with large data type.</span></span> <span data-ttu-id="a7b87-106">Si hay más de una columna con el tipo de datos de gran tamaño en una tabla única interfaz, el adaptador expone muchas leerán y actualización operaciones para esa tabla de interfaz.</span><span class="sxs-lookup"><span data-stu-id="a7b87-106">If there is more than one column with large data type in a single interface table, the adapter exposes as many read and update operations for that interface table.</span></span>  
  
-   <span data-ttu-id="a7b87-107">Para las columnas de tipo BFILE, los clientes de adaptador solo pueden leer los datos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-107">For columns of type BFILE, adapter clients can only read data.</span></span> <span data-ttu-id="a7b87-108">El adaptador expone Read_\<*LOBColName* \> operación para leer datos de las columnas de tipo BFILE.</span><span class="sxs-lookup"><span data-stu-id="a7b87-108">The adapter exposes Read_\<*LOBColName*\> operation to read data from columns of BFILE type.</span></span> <span data-ttu-id="a7b87-109">Si hay más de una columna con el tipo de datos de gran tamaño en una tabla única interfaz, el adaptador se expone como muchas operaciones de la tabla de interfaz de lectura.</span><span class="sxs-lookup"><span data-stu-id="a7b87-109">If there is more than one column with large data type in a single interface table, the adapter exposes as many read operations for the interface table.</span></span>  
  
 <span data-ttu-id="a7b87-110">Para obtener más información acerca de estas operaciones, vea [operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen LOB datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-110">For more information about these operations, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="a7b87-111">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="a7b87-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="a7b87-112">El ejemplo de este tema actualiza una columna BLOB (fotografía) en la tabla de base de datos de cliente y, a continuación, recupera los datos de la misma columna.</span><span class="sxs-lookup"><span data-stu-id="a7b87-112">The example in this topic updates a BLOB column (PHOTO) in the CUSTOMER database table and then retrieves the data from the same column.</span></span> <span data-ttu-id="a7b87-113">La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-113">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="a7b87-114">Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="a7b87-115">Obtener un ejemplo, **LargeDataTypes_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-115">A sample, **LargeDataTypes_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7b87-116">Este tema enumeran las tareas detalladas de actualización y la lectura de las columnas de tipos de datos de gran tamaño en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-116">This topic lists detailed tasks for updating and reading columns of large data types in a base database table.</span></span> <span data-ttu-id="a7b87-117">Debe realizar el mismo conjunto de tareas para actualizar y leer las columnas de tipos de datos de gran tamaño en una tabla de interfaz.</span><span class="sxs-lookup"><span data-stu-id="a7b87-117">You must perform the same set of tasks for updating and reading columns of large data types in an interface table.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="a7b87-118">La clase de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a7b87-118">The WCF Client Class</span></span>  
 <span data-ttu-id="a7b87-119">El nombre del cliente WCF generado para las operaciones en tablas con tipos de datos de gran tamaño mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se basa en el nombre de la tabla, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7b87-119">The name of the WCF client generated for the operations on tables with large data types by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is based on the name of the table, as listed in the following table.</span></span>  
  
|<span data-ttu-id="a7b87-120">Artefacto</span><span class="sxs-lookup"><span data-stu-id="a7b87-120">Artifact</span></span>|<span data-ttu-id="a7b87-121">Nombre de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a7b87-121">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="a7b87-122">Tablas de interfaz</span><span class="sxs-lookup"><span data-stu-id="a7b87-122">Interface tables</span></span>|<span data-ttu-id="a7b87-123">InterfaceTables_ [APP_NAME] _ [esquema]\_cliente [NombreTabla]</span><span class="sxs-lookup"><span data-stu-id="a7b87-123">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
  
 <span data-ttu-id="a7b87-124">[APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.</span><span class="sxs-lookup"><span data-stu-id="a7b87-124">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="a7b87-125">[Esquema] = colección de artefactos; Por ejemplo, las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a7b87-125">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="a7b87-126">[NombreTabla] = el nombre de la tabla. Por ejemplo, MS_SAMPLE_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="a7b87-126">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="a7b87-127">[VIEW_NAME] = el nombre de la vista; Por ejemplo, MS_SAMPLE_EMPLOYEE_View.</span><span class="sxs-lookup"><span data-stu-id="a7b87-127">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="a7b87-128">Firma de método para invocar operaciones en tablas</span><span class="sxs-lookup"><span data-stu-id="a7b87-128">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="a7b87-129">La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a7b87-129">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="a7b87-130">Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a7b87-130">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="a7b87-131">Operación</span><span class="sxs-lookup"><span data-stu-id="a7b87-131">Operation</span></span>|<span data-ttu-id="a7b87-132">Firma de método</span><span class="sxs-lookup"><span data-stu-id="a7b87-132">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="a7b87-133">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="a7b87-133">Update_\<*column_name*\></span></span>|<span data-ttu-id="a7b87-134">Update_ void público\<*column_name*\>(cadena de filtro, byte [] datos;)</span><span class="sxs-lookup"><span data-stu-id="a7b87-134">public void Update_\<*column_name*\>(string FILTER, byte[] DATA);</span></span>|  
|<span data-ttu-id="a7b87-135">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="a7b87-135">Read_\<*column_name*\></span></span>|<span data-ttu-id="a7b87-136">pública System.IO.Stream Read_\<*column_name*\>(cadena de filtro;)</span><span class="sxs-lookup"><span data-stu-id="a7b87-136">public System.IO.Stream Read_\<*column_name*\>(string FILTER);</span></span>|  
  
 <span data-ttu-id="a7b87-137">Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones de Update_PHOTO y Read_PHOTO en la tabla de base de datos de cliente en el esquema de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a7b87-137">As an example, the following code shows the method signatures for a WCF client class generated for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table under the APPS schema.</span></span>  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 <span data-ttu-id="a7b87-138">En este fragmento de código, **Tables_APPS_CUSTOMERClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b87-138">In this snippet, **Tables_APPS_CUSTOMERClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="a7b87-139">Update_PHOTO y Read_PHOTO son métodos que se pueden invocar para actualizar y leer las columnas de tipos de datos de gran tamaño en una tabla.</span><span class="sxs-lookup"><span data-stu-id="a7b87-139">Update_PHOTO and Read_PHOTO are methods that can be invoked to update and read columns of large data types in a table.</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="a7b87-140">Parámetros para las operaciones de tabla</span><span class="sxs-lookup"><span data-stu-id="a7b87-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="a7b87-141">Esta sección proporciona los parámetros requeridos por la Update_\<*column_name* \> y Read_\<*column_name* \> operación.</span><span class="sxs-lookup"><span data-stu-id="a7b87-141">This section provides the parameters required by the Update_\<*column_name*\> and Read_\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="a7b87-142">Nombre de la operación</span><span class="sxs-lookup"><span data-stu-id="a7b87-142">Operation name</span></span>|<span data-ttu-id="a7b87-143">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7b87-143">Parameters</span></span>|  
|--------------------|----------------|  
|<span data-ttu-id="a7b87-144">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="a7b87-144">Update_\<*column_name*\></span></span>|<span data-ttu-id="a7b87-145">Necesita los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a7b87-145">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="a7b87-146">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-146">-   `string FILTER`.</span></span> <span data-ttu-id="a7b87-147">Este parámetro debe contener where cláusula que denota el registro para el que se tienen que actualizar datos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-147">This parameter must contain the where clause that denotes the record for which data has to be updated.</span></span> <span data-ttu-id="a7b87-148">Por ejemplo, `"WHERE Name='Mindy Martin'"`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-148">For example, `"WHERE Name='Mindy Martin'"`.</span></span><br /><span data-ttu-id="a7b87-149">-   `byte[] DATA`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-149">-   `byte[] DATA`.</span></span> <span data-ttu-id="a7b87-150">Contiene una matriz de bytes de datos que se van a actualizar en una columna de tipo de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a7b87-150">Contains a byte array of data to be update in a column of large data type.</span></span>|  
|<span data-ttu-id="a7b87-151">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="a7b87-151">Read_\<*column_name*\></span></span>|<span data-ttu-id="a7b87-152">Necesita los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a7b87-152">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="a7b87-153">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-153">-   `string FILTER`.</span></span> <span data-ttu-id="a7b87-154">Este parámetro debe contener where cláusula que denota el registro desde el que los datos tienen que debe leerse.</span><span class="sxs-lookup"><span data-stu-id="a7b87-154">This parameter must contain the where clause that denotes the record from which the data has to be read.</span></span> <span data-ttu-id="a7b87-155">Por ejemplo, `"WHERE Name='Mindy Martin'"`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-155">For example, `"WHERE Name='Mindy Martin'"`.</span></span>|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a><span data-ttu-id="a7b87-156">Creación de un cliente WCF para invocar operaciones en tablas con columnas de tipos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="a7b87-156">Creating a WCF Client to Invoke Operations on Tables with Columns of Large Data Types</span></span>  
 <span data-ttu-id="a7b87-157">El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-157">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="a7b87-158">En esta sección se describe cómo crear un cliente WCF para invocar operaciones Update_PHOTO y Read_PHOTO en una tabla de base de datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="a7b87-158">This section describes how to create a WCF client to invoke Update_PHOTO and Read_PHOTO operations on a CUSTOMER database table.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="a7b87-159">Para crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a7b87-159">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="a7b87-160">Cree un proyecto de Visual C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7b87-160">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="a7b87-161">De este tema, cree una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a7b87-161">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="a7b87-162">Genere la clase de cliente WCF para las operaciones de Update_PHOTO y Read_PHOTO en la tabla de base de datos de cliente.</span><span class="sxs-lookup"><span data-stu-id="a7b87-162">Generate the WCF client class for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table.</span></span> <span data-ttu-id="a7b87-163">Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-163">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a7b87-164">Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.</span><span class="sxs-lookup"><span data-stu-id="a7b87-164">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="a7b87-165">En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`, `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-165">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`, `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="a7b87-166">Abra el archivo Program.cs y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7b87-166">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  <span data-ttu-id="a7b87-167">Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.</span><span class="sxs-lookup"><span data-stu-id="a7b87-167">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="a7b87-168">En este fragmento de código, `Tables_APPS_CUSTOMERClient` es el cliente WCF definido en OracleEBSBindingClient.cs.</span><span class="sxs-lookup"><span data-stu-id="a7b87-168">In this snippet, `Tables_APPS_CUSTOMERClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="a7b87-169">Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b87-169">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7b87-170">En este fragmento de código, se utiliza el enlace y la dirección del extremo de app.config de archivo de configuración. Puede especificar también explícitamente estos valores en el código.</span><span class="sxs-lookup"><span data-stu-id="a7b87-170">In this snippet, you use the binding and endpoint address from the configuration file app.config. You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="a7b87-171">Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-171">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="a7b87-172">Establezca las credenciales para el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7b87-172">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a7b87-173">En este ejemplo, que se están realizando operaciones en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7b87-173">In this example, you are performing operations on a database table.</span></span> <span data-ttu-id="a7b87-174">Sin embargo, si va a realizar las operaciones en una tabla de interfaz, debe establecer el contexto de la aplicación especificando los valores adecuados para el **OracleUserName**, **OraclePassword**, y  **OracleEBSResponsibilityName** propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="a7b87-174">However, if you are performing operations on an interface table, you must set the application context by specifying appropriate values for the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="a7b87-175">Debe especificar estas propiedades de enlace antes de abrir al cliente.</span><span class="sxs-lookup"><span data-stu-id="a7b87-175">You must specify these binding properties before opening the client.</span></span> <span data-ttu-id="a7b87-176">Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span><span class="sxs-lookup"><span data-stu-id="a7b87-176">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
7.  <span data-ttu-id="a7b87-177">Abra al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a7b87-177">Open the client as described in the snippet below:</span></span>  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
8.  <span data-ttu-id="a7b87-178">Invocar la operación Update_PHOTO en la tabla CUSTOMER.</span><span class="sxs-lookup"><span data-stu-id="a7b87-178">Invoke the Update_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="a7b87-179">La operación de Update_PHOTO requiere una matriz de bytes para los datos que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7b87-179">The Update_PHOTO operation requires a byte array for the data to be updated.</span></span> <span data-ttu-id="a7b87-180">En este fragmento de código, se utiliza la clase de FileStream para crear una matriz de bytes para una foto, SamplePhoto.jpg.</span><span class="sxs-lookup"><span data-stu-id="a7b87-180">In this code snippet, you use the FileStream class to create a byte array for a photo, SamplePhoto.jpg.</span></span> <span data-ttu-id="a7b87-181">Para que funcione la aplicación, el archivo debe copiarse al directorio bin del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a7b87-181">For this application to work, the file must be copied to the project’s bin directory.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a7b87-182">La operación de Update_PHOTO se debe realizar en una transacción, por lo que la **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true** y se debe realizar la operación de Update_PHOTO dentro de un ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="a7b87-182">The Update_PHOTO operation must be performed in a transaction, so the **UseAmbientTransaction** binding property must be set to **true** and the Update_PHOTO operation must be performed within a transaction scope.</span></span> <span data-ttu-id="a7b87-183">Puede establecer la **UseAmbientTransaction** propiedad de enlace en el archivo app.config o si se establece explícitamente en la aplicación como `binding.UseAmbientTransaction = true`.</span><span class="sxs-lookup"><span data-stu-id="a7b87-183">You can set the **UseAmbientTransaction** binding property either in the app.config or by explicitly setting it in your application as `binding.UseAmbientTransaction = true`.</span></span> <span data-ttu-id="a7b87-184">Tenga en cuenta que si va a especificar explícitamente la propiedad de enlace en el código, debe hacerlo antes de abrir al cliente.</span><span class="sxs-lookup"><span data-stu-id="a7b87-184">Note that if you are specifying the binding property explicitly in the code, you must do so before opening the client.</span></span>  
  
    ```  
    byte[] photo;  
  
    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
    {  
        try  
        {  
            Console.WriteLine("Reading the photo");  
            int count = 0;  
            photo = new byte[fs.Length];  
            while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) < fs.Length) ;  
        }  
        catch(Exception ex)  
        {  
            Console.WriteLine("Exception: " + ex.Message);  
            throw;  
        }  
    }  
  
    Console.WriteLine("Updating data for the 'PHOTO' column");  
    // Invoking the Update_PHOTO operation inside a transaction scope  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Name='Mindy Martin'";  
        client.Update_PHOTO(filter, photo);  
        tx.Complete();  
    }  
  
    ```  
  
9. <span data-ttu-id="a7b87-185">Invocar la operación Read_PHOTO en la tabla CUSTOMER.</span><span class="sxs-lookup"><span data-stu-id="a7b87-185">Invoke the Read_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="a7b87-186">El Read_PHOTO da el resultado en forma de System.IO.Stream.</span><span class="sxs-lookup"><span data-stu-id="a7b87-186">The Read_PHOTO gives the output in the form of System.IO.Stream.</span></span> <span data-ttu-id="a7b87-187">El cliente de adaptador debe implementar la clase FileStream para leer los datos de la operación de Read_PHOTO.</span><span class="sxs-lookup"><span data-stu-id="a7b87-187">The adapter client must implement the FileStream class to read the data from Read_PHOTO operation.</span></span> <span data-ttu-id="a7b87-188">Una vez completada la operación de Read_PHOTO, un archivo PhotoCopy.jpg se copia en el directorio bin del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a7b87-188">After the Read_PHOTO operation is complete, a file PhotoCopy.jpg is copied under the project’s bin directory.</span></span>  
  
    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  
  
    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  
  
10. <span data-ttu-id="a7b87-189">Cierre al cliente como se describe en el siguiente fragmento:</span><span class="sxs-lookup"><span data-stu-id="a7b87-189">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="a7b87-190">Compile el proyecto y, a continuación, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="a7b87-190">Build the project and then run it.</span></span> <span data-ttu-id="a7b87-191">La aplicación actualiza la columna PHOTO de la tabla CUSTOMER y, a continuación, lee el contenido de la columna PHOTO.</span><span class="sxs-lookup"><span data-stu-id="a7b87-191">The application updates the PHOTO column of the CUSTOMER table and then reads the content of the PHOTO column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b87-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7b87-192">See Also</span></span>  
 [<span data-ttu-id="a7b87-193">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="a7b87-193">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)