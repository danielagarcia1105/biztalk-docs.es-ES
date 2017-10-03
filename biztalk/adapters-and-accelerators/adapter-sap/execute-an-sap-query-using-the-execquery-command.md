---
title: Ejecutar una consulta SAP mediante el comando EXECQUERY | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 520153bf-9477-4b35-8953-3f5cb444ab9f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86159a03858ae5aa31bb37da56b6e5ea68dac3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="execute-an-sap-query-using-the-execquery-command"></a><span data-ttu-id="63e89-102">Ejecutar una consulta SAP mediante el comando EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="63e89-102">Execute an SAP Query Using the EXECQUERY Command</span></span>
<span data-ttu-id="63e89-103">La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="63e89-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="63e89-104">Con el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], puede ejecutar las consultas predefinidas en el sistema SAP mediante la ejecución de una instrucción EXECQUERY.</span><span class="sxs-lookup"><span data-stu-id="63e89-104">With the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], you can execute pre-defined queries in the SAP system by executing an EXECQUERY statement.</span></span>  
  
## <a name="how-to-perform-a-query-by-using-the-execquery-command"></a><span data-ttu-id="63e89-105">Cómo realizar una consulta mediante el comando EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="63e89-105">How to Perform a Query by Using the EXECQUERY Command</span></span>  
 <span data-ttu-id="63e89-106">Para ejecutar SAP predefinido de consultas usando la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="63e89-106">To execute pre-defined SAP queries using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-perform-a-query"></a><span data-ttu-id="63e89-107">Para realizar una consulta</span><span class="sxs-lookup"><span data-stu-id="63e89-107">To perform a query</span></span>  
  
1.  <span data-ttu-id="63e89-108">Incluir una referencia (y una con la instrucción en el código) para **Microsoft.Data.SAPClient**.</span><span class="sxs-lookup"><span data-stu-id="63e89-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2.  <span data-ttu-id="63e89-109">Crear un **SAPConnection** objeto mediante un proveedor de datos de cadena de conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="63e89-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="63e89-110">Para obtener más información acerca de la cadena de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="63e89-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3.  <span data-ttu-id="63e89-111">Abrir una conexión con el sistema SAP mediante la invocación de **abiertos** en el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="63e89-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4.  <span data-ttu-id="63e89-112">Crear un **SAPCommand** objeto desde el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="63e89-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5.  <span data-ttu-id="63e89-113">Especifique la instrucción EXECQUERY en el **CommandText** propiedad de la **SAPCommand**.</span><span class="sxs-lookup"><span data-stu-id="63e89-113">Specify the EXECQUERY statement in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="63e89-114">Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos.</span><span class="sxs-lookup"><span data-stu-id="63e89-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="63e89-115">Para obtener más información acerca de cómo ejecutar consultas definidas en un sistema SAP mediante una instrucción EXECQUERY, consulte [sintaxis de una instrucción EXECQUERY en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="63e89-115">For more information about how to execute queries defined in an SAP system using an EXECQUERY statement, see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
6.  <span data-ttu-id="63e89-116">Ejecute el comando para realizar la consulta y obtener los resultados en un **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="63e89-116">Execute the command to perform the query and obtain the results in a **SAPDataReader**.</span></span>  
  
7.  <span data-ttu-id="63e89-117">Lea los resultados de la **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="63e89-117">Read the results from the **SAPDataReader**.</span></span>  
  
8.  <span data-ttu-id="63e89-118">Cuando haya terminado de usarlos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="63e89-118">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
 <span data-ttu-id="63e89-119">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos.</span><span class="sxs-lookup"><span data-stu-id="63e89-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="63e89-120">Para obtener más información acerca de las clases ADO.NET que se extiende el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="63e89-120">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e89-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63e89-121">Example</span></span>  
 <span data-ttu-id="63e89-122">En el ejemplo siguiente se escribe los resultados de una consulta, ZTEST1, en la consola.</span><span class="sxs-lookup"><span data-stu-id="63e89-122">The following example writes the results of a query, ZTEST1, to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExecQuery  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
           string connstr = "TYPE=A; ASHOST=YourSapHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
           using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "EXECQUERY ZTEST1 @userGRoup='SYSTQV000024',@P1='0000001390',@P2='0000080150'";  
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
  
## <a name="see-also"></a><span data-ttu-id="63e89-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="63e89-123">See Also</span></span>  
 [<span data-ttu-id="63e89-124">Usar el proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="63e89-124">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)  
 [<span data-ttu-id="63e89-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="63e89-125">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)