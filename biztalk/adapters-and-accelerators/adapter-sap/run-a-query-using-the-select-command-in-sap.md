---
title: Ejecutar una consulta con el comando SELECT en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SELECT command, performing a query
- query, performing by using the SELECT command
ms.assetid: 6f03243c-ef50-4a4a-8fe6-4e525bd7efe3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e03ac093e0fb7b2b8f95d770661bd702d988f01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-query-using-the-select-command-in-sap"></a><span data-ttu-id="2df82-102">Ejecutar una consulta con el comando SELECT en SAP</span><span class="sxs-lookup"><span data-stu-id="2df82-102">Run a Query Using the SELECT Command in SAP</span></span>
<span data-ttu-id="2df82-103">La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2df82-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="2df82-104">Con el [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], puede consultar los artefactos SAP mediante la ejecución de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="2df82-104">With the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can query SAP artifacts by executing a SELECT statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-select-command"></a><span data-ttu-id="2df82-105">Cómo realizar una consulta mediante el comando SELECT</span><span class="sxs-lookup"><span data-stu-id="2df82-105">How to Perform a Query by Using the SELECT Command</span></span>  
 <span data-ttu-id="2df82-106">Para los artefactos SAP de consulta mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2df82-106">To query SAP artifacts using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="2df82-107">Para realizar una consulta</span><span class="sxs-lookup"><span data-stu-id="2df82-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="2df82-108">Incluir una referencia (y una con la instrucción en el código) para **Microsoft.Data.SAPClient**.</span><span class="sxs-lookup"><span data-stu-id="2df82-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="2df82-109">Crear un **SAPConnection** objeto mediante un proveedor de datos de cadena de conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="2df82-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="2df82-110">Para obtener más información acerca de la cadena de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="2df82-111">Abrir una conexión con el sistema SAP mediante la invocación de **abiertos** en el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="2df82-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="2df82-112">Crear un **SAPCommand** objeto desde el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="2df82-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="2df82-113">Especifique la instrucción SELECT en la **CommandText** propiedad de la **SAPCommand**.</span><span class="sxs-lookup"><span data-stu-id="2df82-113">Specify the SELECT statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="2df82-114">Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos.</span><span class="sxs-lookup"><span data-stu-id="2df82-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="2df82-115">Para obtener más información sobre cómo consultar los artefactos SAP mediante una instrucción SELECT, vea [sintaxis para una instrucción SELECT en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-115">For more information about how to query SAP artifacts using a SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="2df82-116">Para obtener ejemplos de cómo especificar un BAPI o RFC, consulte [ejemplos de la instrucción SELECT](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-116">For examples of how to specify a BAPI or RFC, see [Examples for SELECT Statement](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md).</span></span>  
  
6.  <span data-ttu-id="2df82-117">Ejecute el comando para realizar la consulta y obtener los resultados en un **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="2df82-117">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="2df82-118">Lea los resultados de la **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="2df82-118">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="2df82-119">Cuando haya terminado de usarlos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="2df82-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="2df82-120">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos.</span><span class="sxs-lookup"><span data-stu-id="2df82-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="2df82-121">Para obtener más información acerca de las clases ADO.NET que se extiende el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="2df82-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df82-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2df82-122">Example</span></span>  
 <span data-ttu-id="2df82-123">En el ejemplo siguiente se escribe los resultados de una instrucción select en una instrucción de combinación interna con parámetros en la consola.</span><span class="sxs-lookup"><span data-stu-id="2df82-123">The following example writes the results of a select on a parameterized inner join statement to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoSelect  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        /// <summary>  
        /// select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid  
        /// </summary>  
  
        string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "select top 1 * from sflight inner join spfli on sflight.connid = spfli.connid where spfli.connid = @connid";  
                    cmd.Parameters.Add(new SAPParameter("@connid", 17));                      
                    using (SAPDataReader dr = cmd.ExecuteReader())  
                    {  
                        do  
                        {  
                            int rows = 0;  
                            while (dr.Read())  
                            {  
                                rows++;  
                                StringBuilder b = new StringBuilder();  
                                for (int i = 0; i < dr.FieldCount; i++)  
                                {  
                                    b.Append(dr[i].ToString()+" ");  
                                }  
                                Console.WriteLine("row {0}: {1} ", rows, b.ToString());  
                            }  
                            Console.WriteLine("Number of rows:{0}", rows);  
  
                        } while (dr.NextResult());  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2df82-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df82-124">See Also</span></span>  
 <span data-ttu-id="2df82-125">[Usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="2df82-125">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="2df82-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2df82-126">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)