---
title: Ejemplo de GetMessages | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ebc4ce5b87a0b698f0295fdf29c8f7138efed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getmessages-sample"></a><span data-ttu-id="a87c3-102">Ejemplo de GetMessages</span><span class="sxs-lookup"><span data-stu-id="a87c3-102">GetMessages Sample</span></span>
<span data-ttu-id="a87c3-103">En este tema se proporciona código de ejemplo que puede utilizar para recuperar mensajes de una de las tablas sin repudio de mensajes o una de las tablas de línea de negocio (LOB) en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="a87c3-103">This topic provides sample code that you can use to retrieve messages from one of the message non-repudiation tables or one of the line-of-business (LOB) tables in a readable form.</span></span> <span data-ttu-id="a87c3-104">Las tablas sin repudio de mensajes incluyen MessageStorageIn y MessageStorageOut de la [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]base de datos de archivo; las tablas LOB incluyen MessageFromLOB y MessageToLOB en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos.</span><span class="sxs-lookup"><span data-stu-id="a87c3-104">The message non-repudiation tables include MessageStorageIn and MessageStorageOut in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive database; the LOB tables include MessageFromLOB and MessageToLOB in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span>  
  
 <span data-ttu-id="a87c3-105">Use `GetMessages` para solucionar problemas o desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a87c3-105">Use `GetMessages` for either troubleshooting or development.</span></span> <span data-ttu-id="a87c3-106">De forma predeterminada, el código devuelve una cadena en base 64.</span><span class="sxs-lookup"><span data-stu-id="a87c3-106">By default, the code returns a base 64 string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a87c3-107">El código de ejemplo GetMessages.cs contiene dos secciones de código: uno para recuperar mensajes de una de las tablas LOB y otro para recuperar mensajes de una de las tablas sin repudio.</span><span class="sxs-lookup"><span data-stu-id="a87c3-107">The GetMessages.cs sample code contains two sections of code—one for retrieving messages from one of the LOB tables, and one for retrieving messages from one of the non-repudiation tables.</span></span> <span data-ttu-id="a87c3-108">Crear aplicaciones independientes para cada propósito.</span><span class="sxs-lookup"><span data-stu-id="a87c3-108">Create separate applications for each purpose.</span></span>  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a><span data-ttu-id="a87c3-109">Para recuperar mensajes de una tabla LOB</span><span class="sxs-lookup"><span data-stu-id="a87c3-109">To retrieve messages from an LOB table</span></span>  
  
1.  <span data-ttu-id="a87c3-110">Agregue el siguiente código de ejemplo para el programa:</span><span class="sxs-lookup"><span data-stu-id="a87c3-110">Add the following sample code to your program:</span></span>  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="a87c3-111">Establecer el `sMessageSource` parámetro a la tabla del MessagesFromLOB o MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="a87c3-111">Set the `sMessageSource` parameter to either the MessagesFromLOB or MessagesToLOB table.</span></span>  
  
3.  <span data-ttu-id="a87c3-112">Establecer el `sMessageID` parámetro en el valor de la **MessageID** campo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a87c3-112">Set the `sMessageID` parameter to the value of the **MessageID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a87c3-113">La aplicación devuelve una cadena que contiene el mensaje recuperado.</span><span class="sxs-lookup"><span data-stu-id="a87c3-113">The application returns a string that contains the retrieved message.</span></span>  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a><span data-ttu-id="a87c3-114">Para recuperar mensajes de una tabla sin repudio</span><span class="sxs-lookup"><span data-stu-id="a87c3-114">To retrieve messages from a non-repudiation table</span></span>  
  
1.  <span data-ttu-id="a87c3-115">Agregue el siguiente código de ejemplo para el programa:</span><span class="sxs-lookup"><span data-stu-id="a87c3-115">Add the following sample code to your program:</span></span>  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  <span data-ttu-id="a87c3-116">Establecer el `sMessageSource` parámetro a la tabla del MessageStorageIn o MessageStorageOut.</span><span class="sxs-lookup"><span data-stu-id="a87c3-116">Set the `sMessageSource` parameter to either the MessageStorageIn or MessageStorageOut table.</span></span>  
  
3.  <span data-ttu-id="a87c3-117">Establecer el `sMessageID` parámetro en el valor de la **RecordID** campo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a87c3-117">Set the `sMessageID` parameter to the value of the **RecordID** field in the database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a87c3-118">La aplicación devuelve una cadena que contiene el mensaje recuperado.</span><span class="sxs-lookup"><span data-stu-id="a87c3-118">The application returns a string that contains the retrieved message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a87c3-119">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="a87c3-119">Demonstrates</span></span>  
 <span data-ttu-id="a87c3-120">El ejemplo de GetMessages incluye las siguientes dos secciones de código:</span><span class="sxs-lookup"><span data-stu-id="a87c3-120">The GetMessages sample includes the following two sections of code:</span></span>  
  
-   <span data-ttu-id="a87c3-121">Una sección muestra cómo recuperar un mensaje binario de una de las tablas sin repudio y convertirlos a un formato legible ASCII.</span><span class="sxs-lookup"><span data-stu-id="a87c3-121">One section shows you how to retrieve a binary message from one of the non-repudiation tables, and convert it into readable ASCII form.</span></span>  
  
-   <span data-ttu-id="a87c3-122">La otra sección muestra cómo recuperar un mensaje de una de las tablas LOB.</span><span class="sxs-lookup"><span data-stu-id="a87c3-122">The other section shows you how to retrieve a message from one of the LOB tables.</span></span> <span data-ttu-id="a87c3-123">Dado que un mensaje en una tabla LOB ya está en formato ASCII, esto es una instrucción select de SQL.</span><span class="sxs-lookup"><span data-stu-id="a87c3-123">Because a message in an LOB table is already in ASCII form, this is a SQL select statement.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a87c3-124">Con fines de demostración, el código de ejemplo proporcionado utiliza una instrucción directa de SQL que es susceptibles de vulnerabilidades de inyección de SQL.</span><span class="sxs-lookup"><span data-stu-id="a87c3-124">For demonstration purposes, the sample code provided uses a direct SQL statement that is prone to SQL injection vulnerabilities.</span></span> <span data-ttu-id="a87c3-125">En un entorno de producción, se recomienda utilizar procedimientos almacenados de SQL con parámetros, en lugar de la instrucción SQL directa, para evitar estas vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="a87c3-125">In a production environment, it is recommended that you use parameterized SQL stored procedures, instead of the direct SQL statement, to prevent such vulnerabilities.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a87c3-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a87c3-126">Example</span></span>  
 <span data-ttu-id="a87c3-127">Utilice una de las dos secciones en el siguiente ejemplo de código para recuperar mensajes de una de las tablas sin repudio o una de las tablas LOB.</span><span class="sxs-lookup"><span data-stu-id="a87c3-127">Use one of the two sections in the following code example for retrieving messages from one of the non-repudiation tables or one of the LOB tables.</span></span>  
  
```  
using System;  
using System.Text;  
using System.Data.SqlClient;   
using Microsoft.Solutions.BTARN.Shared;  
  
namespace Microsoft.Solutions.BTARN.Admin  
{  
  
      /// <summary>  
      /// Summary description for GetMessages.  
      /// </summary>  
      class GetMessages  
      {  
            /// <summary>  
            /// The main entry point for the application.  
            /// </summary>  
            [STAThread]  
            static void Main(string[] args)  
            {  
                  Console.WriteLine(GetLOBMessage("MessagesFromLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetLOBMessage("MessagesToLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetNRMessage("MessageStorageIn", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
                  Console.WriteLine(GetNRMessage("MessageStorageOut", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
            }  
  
            /// <summary>  
            /// Retrieve a message from the LOB tables in the BTARNDATA database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessagesFromLOB or MessagesToLOB</param>  
            /// <param name="sMessageID">The value of the MessageID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>        
            private static string GetLOBMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.DataDbConnectionString);  
                  sQuery = "SELECT ServiceContent from " + sMessageSource + " WHERE MessageID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                        sReturnedMessage=localReader.GetString(0);  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
  
            /// <summary>  
            /// Retrieve a message from the non-repudiation tables in the BTARNArchive database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessageStorageIn or MessageStorageOut</param>  
            /// <param name="sMessageID">The value of the RecordID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>  
            private static string GetNRMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.ArchiveDbConnectionString);  
                  sQuery = "SELECT Content from " + sMessageSource + " WHERE RecordID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                  {  
                        //Determine the size of the field in bytes and create a new byte array  
                        byte[] bData= new byte[localReader.GetBytes(0, 0, null, 0, 0)];  
  
                        //Read the value of the field into bData  
                        localReader.GetBytes(0, 0, bData, 0, bData.Length);  
  
                        //Convert the byte array into a string  
                        sReturnedMessage=Encoding.ASCII.GetString(bData);  
                  }  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
      }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a87c3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a87c3-128">See Also</span></span>  
 [<span data-ttu-id="a87c3-129">Ejemplos de mensajería</span><span class="sxs-lookup"><span data-stu-id="a87c3-129">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)