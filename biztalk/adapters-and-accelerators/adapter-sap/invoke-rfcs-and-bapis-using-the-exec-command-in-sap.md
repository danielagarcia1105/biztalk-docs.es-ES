---
title: Invocar RFC y BAPI mediante el comando EXEC en SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC command, invoking RFCs and BAPIs
- BAPIs and RFCs, invoking by using the EXEC command
- RFCs and BAPIs, invoking by using the EXEC command
ms.assetid: 55443679-2fa8-4c13-ac3b-1c85b5166cd2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7ddd9e4d3e7d4c4d34445c7a42d83262d04f4b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988197"
---
# <a name="invoke-rfcs-and-bapis-using-the-exec-command-in-sap"></a><span data-ttu-id="87cf6-102">Invocar RFC y BAPI mediante el comando EXEC en SAP</span><span class="sxs-lookup"><span data-stu-id="87cf6-102">Invoke RFCs and BAPIs using the EXEC Command in SAP</span></span>
<span data-ttu-id="87cf6-103">La [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] expone el sistema SAP como un origen de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="87cf6-103">The [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] exposes the SAP system as an ADO.NET data source.</span></span> <span data-ttu-id="87cf6-104">Mediante el uso de [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], puede invocar RFC y BAPI en el sistema SAP a través de un comando EXEC.</span><span class="sxs-lookup"><span data-stu-id="87cf6-104">By using [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], you can invoke RFCs and BAPIs on the SAP system through an EXEC command.</span></span>  
  
## <a name="how-to-invoke-rfcs-and-bapis-on-the-sap-system"></a><span data-ttu-id="87cf6-105">Cómo invocar RFC y BAPI en el sistema SAP</span><span class="sxs-lookup"><span data-stu-id="87cf6-105">How to Invoke RFCs and BAPIs on the SAP system</span></span>  
 <span data-ttu-id="87cf6-106">Para invocar una RFC o BAPI utilizando el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="87cf6-106">To invoke an RFC or BAPI using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], perform the following steps:</span></span>  
  
#### <a name="to-invoke-an-rfc-or-bapi"></a><span data-ttu-id="87cf6-107">Para invocar una RFC o BAPI</span><span class="sxs-lookup"><span data-stu-id="87cf6-107">To invoke an RFC or BAPI</span></span>  
  
1. <span data-ttu-id="87cf6-108">Incluir una referencia (y una instrucción using en el código) para **Microsoft.Data.SAPClient**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-108">Include a reference (and a using statement in your code) to **Microsoft.Data.SAPClient**.</span></span>  
  
2. <span data-ttu-id="87cf6-109">Crear un **SAPConnection** objeto mediante el uso de un proveedor de datos de cadena de conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="87cf6-109">Create a **SAPConnection** object by using a Data Provider for SAP connection string.</span></span> <span data-ttu-id="87cf6-110">Para obtener más información acerca de la cadena de conexión, consulte [lea acerca de los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="87cf6-110">For more information about the connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
3. <span data-ttu-id="87cf6-111">Abrir una conexión con el sistema SAP mediante la invocación **abierto** en el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-111">Open a connection to the SAP system by invoking **Open** on the **SAPConnection**.</span></span>  
  
4. <span data-ttu-id="87cf6-112">Crear un **SAPCommand** objeto desde el **SAPConnection**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-112">Create a **SAPCommand** object from the **SAPConnection**.</span></span>  
  
5. <span data-ttu-id="87cf6-113">Especifique la llamada BAPI o RFC en los **CommandText** propiedad de la **SAPCommand**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-113">Specify the BAPI or RFC call in the **CommandText** property of the **SAPCommand**.</span></span> <span data-ttu-id="87cf6-114">Si es necesario, puede especificar parámetros mediante **SAPParameter** objetos.</span><span class="sxs-lookup"><span data-stu-id="87cf6-114">If necessary, you can specify parameters using **SAPParameter** objects.</span></span> <span data-ttu-id="87cf6-115">Para obtener más información sobre cómo especificar una llamada BAPI o RFC mediante una instrucción EXEC, consulte [sintaxis para una instrucción EXEC en SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="87cf6-115">For more information about how to specify a BAPI or RFC call using an EXEC statement, see [Syntax for an EXEC Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md).</span></span> <span data-ttu-id="87cf6-116">Para obtener ejemplos de cómo especificar una BAPI o RFC, consulte [ejemplos de la instrucción EXEC](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span><span class="sxs-lookup"><span data-stu-id="87cf6-116">For examples of how to specify a BAPI or RFC, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
6. <span data-ttu-id="87cf6-117">Ejecute el comando para invocar la RFC o BAPI y obtener los resultados en un **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-117">Execute the command to invoke the RFC or BAPI and obtain the results in a **SAPDataReader**.</span></span>  
  
7. <span data-ttu-id="87cf6-118">Lea los resultados de la **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-118">Read the results from the **SAPDataReader**.</span></span>  
  
8. <span data-ttu-id="87cf6-119">Cuando haya terminado con ellos, cerrar (o eliminar) la **SAPConnection** y **SAPDataReader**.</span><span class="sxs-lookup"><span data-stu-id="87cf6-119">When you are finished using them, close (or dispose) the **SAPConnection** and the **SAPDataReader**.</span></span>  
  
   <span data-ttu-id="87cf6-120">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] también expone un **SAPClientFactory** (clase), que puede usar para crear **SAPConnection**, **SAPCommand** y **SAPConnection** objetos.</span><span class="sxs-lookup"><span data-stu-id="87cf6-120">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] also exposes a **SAPClientFactory** class, which you can use to create **SAPConnection**, **SAPCommand** and **SAPConnection** objects.</span></span> <span data-ttu-id="87cf6-121">Para obtener más información acerca de las clases ADO.NET extendida la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [extender Interfaces de ADO.NET con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="87cf6-121">For more information about the ADO.NET classes extended by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Extend ADO.NET Interfaces with the SAP adapter](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87cf6-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87cf6-122">Example</span></span>  
 <span data-ttu-id="87cf6-123">El ejemplo siguiente invoca SD_RFC_CUSTOMER_GET para recuperar la información de cliente para todos los clientes cuyos nombres empiezan por "AB".</span><span class="sxs-lookup"><span data-stu-id="87cf6-123">The following example invokes SD_RFC_CUSTOMER_GET to retrieve customer information for all customers whose names start with "AB".</span></span> <span data-ttu-id="87cf6-124">A continuación, escribe al cliente registros en la consola.</span><span class="sxs-lookup"><span data-stu-id="87cf6-124">It then writes the customer records to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using Microsoft.Data.SAPClient;  
  
namespace SapAdoExec  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string connstr = "TYPE=A; ASHOST=YourSAPHost; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;";  
  
            using (SAPConnection conn = new SAPConnection(connstr))  
            {  
                conn.Open();  
  
                using (SAPCommand cmd = conn.CreateCommand())  
                {  
                    cmd.CommandText = "exec sd_rfc_customer_get @name1='AB*' ";  
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
                                    b.Append(dr[i].ToString() + " ");  
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
  
## <a name="see-also"></a><span data-ttu-id="87cf6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="87cf6-125">See Also</span></span>  
 <span data-ttu-id="87cf6-126">[Usar el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span><span class="sxs-lookup"><span data-stu-id="87cf6-126">[Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md) </span></span>  
 [<span data-ttu-id="87cf6-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="87cf6-127">Samples</span></span>](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)