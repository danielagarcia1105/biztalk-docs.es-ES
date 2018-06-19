---
title: Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be3f829d41b77dc7897d7b3f4300d82e7a3c100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214860"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a><span data-ttu-id="6395b-102">Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6395b-102">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>
<span data-ttu-id="6395b-103">Como un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado, el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un extremo de WS-Metadata Exchange (MEX) que puede usar para recuperar metadatos para operaciones específicas de la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6395b-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
 <span data-ttu-id="6395b-104">WCF proporciona una infraestructura enriquecida para exportar, publicar, recuperar e importar metadatos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="6395b-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="6395b-105">Los servicios WCF, al igual que el adaptador, usan metadatos para describir cómo interactuar con los puntos de conexión de servicio para que las herramientas, como svcutil.exe, puedan generar automáticamente código de cliente para utilizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6395b-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="6395b-106">WCF representa los metadatos para un servicio como una instancia de la **MetadataSet** tipo, que está estrechamente ligado al formato de serialización de metadatos definido en WS-Metadata Exchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="6395b-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="6395b-107">Puede crear un **MetadataSet** para las operaciones de destino en el adaptador mediante el uso de un **MetadataExchangeClient**.</span><span class="sxs-lookup"><span data-stu-id="6395b-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="6395b-108">WCF admite para el intercambio de metadatos es un tema amplio y fuera del ámbito de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="6395b-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="6395b-109">Para obtener más información sobre la compatibilidad con metadatos en WCF, vea [metadatos](https://msdn.microsoft.com/library/ms731823.aspx).</span><span class="sxs-lookup"><span data-stu-id="6395b-109">For more information about support for metadata in WCF, see [Metadata](https://msdn.microsoft.com/library/ms731823.aspx).</span></span> <span data-ttu-id="6395b-110">Para obtener una descripción especialmente apropiada de la arquitectura, clases y espacios de nombres que WCF expone metadatos, vea [Introducción a la arquitectura metadatos](https://msdn.microsoft.com/library/ms730243.aspx).</span><span class="sxs-lookup"><span data-stu-id="6395b-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see [Metadata Architecture Overview](https://msdn.microsoft.com/library/ms730243.aspx).</span></span> <span data-ttu-id="6395b-111">Deberá familiarizarse con el contenido relacionado con la recuperación de metadatos de un servicio WCF en estos temas WCF antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6395b-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="6395b-112">Los temas siguientes contienen información sobre cómo usar un **MetadataExchangeClient** para recuperar los metadatos de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6395b-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="6395b-113">Usar un MetadataExchangeClient para recuperar metadatos</span><span class="sxs-lookup"><span data-stu-id="6395b-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="6395b-114">Para usar un **MetadataExchangeClient** debe especificar un URI de conexión y un enlace (**OracleDBBinding**).</span><span class="sxs-lookup"><span data-stu-id="6395b-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**OracleDBBinding**).</span></span> <span data-ttu-id="6395b-115">El URI de conexión identifica las operaciones para el que van a recuperar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6395b-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="6395b-116">Las secciones siguientes contienen información acerca de cómo especificar las propiedades de enlace importante, el URI de conexión y cómo usar un **MetadataExchangeClient** para recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6395b-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="6395b-117">El URI de conexión</span><span class="sxs-lookup"><span data-stu-id="6395b-117">The Connection URI</span></span>  
 <span data-ttu-id="6395b-118">Para usar el **MetadataExchangeClient** debe proporcionar una URI que especifica un extremo MEX y la o las operaciones para el que van a recuperar los metadatos de la conexión de Oracle.</span><span class="sxs-lookup"><span data-stu-id="6395b-118">To use the **MetadataExchangeClient** you must supply an Oracle connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="6395b-119">Especificar una operación de punto de conexión y de destino MEX en el URI de conexión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6395b-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="6395b-120">Debe incluir el parámetro "wsdl" en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="6395b-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="6395b-121">Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="6395b-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="6395b-122">Si no es el primer parámetro, debe ir precedida por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="6395b-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="6395b-123">Debe seguir el parámetro "wsdl" por uno o más parámetros de "op".</span><span class="sxs-lookup"><span data-stu-id="6395b-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="6395b-124">Cada parámetro de "op" está precedido por una y comercial (&) y especifica la acción de mensaje (Id. de nodo) de una operación de destino.</span><span class="sxs-lookup"><span data-stu-id="6395b-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
 <span data-ttu-id="6395b-125">Por ejemplo, el siguiente URI de conexión tiene como destino las operaciones de inserción y eliminación para el SCOTT. Tabla EMP.</span><span class="sxs-lookup"><span data-stu-id="6395b-125">For example, the following connection URI targets the Insert and Delete operations for the SCOTT.EMP table.</span></span> <span data-ttu-id="6395b-126">Se resaltan los parámetros "wsdl" y "op".</span><span class="sxs-lookup"><span data-stu-id="6395b-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  <span data-ttu-id="6395b-127">Si desea modificar el espacio de nombres generado para la operación de POLLINGSTMT debe especificar un parámetro de PollingId en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="6395b-127">If you want to modify the namespace generated for the POLLINGSTMT operation you should specify a PollingId parameter in the query string.</span></span>  
  
 <span data-ttu-id="6395b-128">Cómo pasar este URI de conexión para el **MetadataExchangeClient** depende de cuál de los métodos sobrecargados que utilice para crear el cliente y recuperar metadatos desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="6395b-128">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="6395b-129">Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="6395b-129">For more information about the Oracle connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="6395b-130">Propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="6395b-130">Binding Properties</span></span>  
 <span data-ttu-id="6395b-131">Cuando se crea el **MetadataExchangeClient**, debe especificar un **OracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="6395b-131">When you create the **MetadataExchangeClient**, you must specify an **OracleDBBinding**.</span></span>  
  
 <span data-ttu-id="6395b-132">Hay varias propiedades de enlace que afectan al modo en que el adaptador genera los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6395b-132">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="6395b-133">Estas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="6395b-133">These properties are:</span></span>  
  
-   <span data-ttu-id="6395b-134">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="6395b-134">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="6395b-135">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="6395b-135">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="6395b-136">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="6395b-136">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6395b-137">Si desea recuperar los metadatos de la operación de POLLINGSTMT debe establecer el **PollingStatement** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="6395b-137">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="6395b-138">Debe asegurarse de que estas propiedades de enlace se establecen en los valores necesarios para la aplicación antes de invocar el **GetMetadata** método en el **MetadataExchangeClient**.</span><span class="sxs-lookup"><span data-stu-id="6395b-138">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="6395b-139">Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6395b-139">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="6395b-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6395b-140">Example</span></span>  
 <span data-ttu-id="6395b-141">En el ejemplo siguiente se usa un **MetadataExchangeClient** para crear una descripción de servicio (documento WSDL) para el Insert, Update, Delete y las operaciones Select en la SCOTT. Tabla EMP.</span><span class="sxs-lookup"><span data-stu-id="6395b-141">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the Insert, Update, Delete, and Select operations on the SCOTT.EMP table.</span></span> <span data-ttu-id="6395b-142">El archivo WSDL se guarda en un archivo, EmpOperations.wsdl.</span><span class="sxs-lookup"><span data-stu-id="6395b-142">The WSDL is saved to a file, EmpOperations.wsdl.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and Oracle Adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Needced for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace OracleMetadataExchange  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            //create a metadata exchange client that will retrieve metadata according to the WS-MEX standard  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "SCOTT";  
            client.SoapCredentials.UserName.Password = "TIGER";  
  
            //set up an endpoint address and specifies the operations for which we want metadata  
            string connectionUri = "oracledb://ADAPTER?wsdl"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //get the metadata  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //get the wsdl from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //save the wsdl to a file  
                wsdl.Write("EmpOperations.wsdl");  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6395b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="6395b-143">See Also</span></span>  
 [<span data-ttu-id="6395b-144">Obtener metadatos mediante programación de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="6395b-144">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)