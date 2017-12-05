---
title: Acerca del archivo de SAPDiscoveredObjects.xml en SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAPDiscoveredObjects.xml
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- Visual Studio DDEX plug-in
ms.assetid: 46ef600d-57ae-4c42-94ce-3099e42482f1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba0c156e2ad6ab0fcbccb5ba7629f63b0aa490e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a><span data-ttu-id="0f835-102">Acerca del archivo de SAPDiscoveredObjects.xml en SAP</span><span class="sxs-lookup"><span data-stu-id="0f835-102">About the SAPDiscoveredObjects.xml File in SAP</span></span>
<span data-ttu-id="0f835-103">Si decide instalar la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, el programa de instalación copia el archivo SAPDiscoveredObjects.xml normalmente en \<unidad de instalación\>: \Program Files\Common archivos \Microsoft Shared\Adapters\SAP.</span><span class="sxs-lookup"><span data-stu-id="0f835-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program copies the SAPDiscoveredObjects.xml file typically at \<installation drive\>:\Program Files\Common Files\Microsoft Shared\Adapters\SAP.</span></span> <span data-ttu-id="0f835-104">El contenido del archivo, después de una instalación nueva de la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="0f835-104">The contents of the file, after a fresh installation of the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], resemble the following.</span></span>  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 <span data-ttu-id="0f835-105">El propósito del archivo SAPDiscoveredObjects.xml es almacenar los objetos SAP (tablas y RFC) que detectan mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] complemento DDEX.</span><span class="sxs-lookup"><span data-stu-id="0f835-105">The purpose of the SAPDiscoveredObjects.xml file is to store the SAP objects (tables and RFCs) that you discover using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="0f835-106">Una vez que ha usado el complemento DDEX para agregar más objetos SAP, se agregan a este archivo XML.</span><span class="sxs-lookup"><span data-stu-id="0f835-106">Once you have used the DDEX plug-in to add more SAP objects, they are added to this XML file.</span></span> <span data-ttu-id="0f835-107">El archivo XML tiene el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="0f835-107">The XML file looks like this.</span></span>  
  
```  
<DiscoveredObjects>  
  <SAP>  
    <Server name="server_name" user="user_name" client="800" type="connection_type">  
      <Tables>  
        <Table>KNA1</Table>  
        <Table>KNAS</Table>  
        <Table>KNAT</Table>  
      </Tables>  
      <RFCs>  
        <RFC>CUSTOMER_CONTACTPS_GET</RFC>  
        <RFC>CUSTOMER_CONTROL_AREA_DATA</RFC>  
        <RFC>CUSTOMER_PARTNERFS_GET</RFC>  
      </RFCs>  
    </Server>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 <span data-ttu-id="0f835-108">El `name` propiedad de la < servidor\> elemento contiene el nombre del servidor que se conecta a mediante el complemento DDEX.</span><span class="sxs-lookup"><span data-stu-id="0f835-108">The `name` property of the <Server\> element contains the name of the server that you connect to using the DDEX plug-in.</span></span> <span data-ttu-id="0f835-109">El `user` y `client` propiedades de la < servidor\> elemento contienen los números de cliente y el nombre de usuario, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0f835-109">The `user` and `client` properties of the <Server\> element contain the user name and client numbers, respectively.</span></span> <span data-ttu-id="0f835-110">El `type` propiedad contiene el tipo de cadena de conexión utilizada para conectarse a un sistema SAP (A, B o D).</span><span class="sxs-lookup"><span data-stu-id="0f835-110">The `type` property contains the type of connection string (A, B, or D) used to connect to an SAP system.</span></span> <span data-ttu-id="0f835-111">Para obtener más información acerca de los tipos de cadenas de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="0f835-111">For more information about the types of connection strings, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
 <span data-ttu-id="0f835-112">El \<tablas\> elemento contiene el nombre de las tablas que se agregan mediante el complemento.</span><span class="sxs-lookup"><span data-stu-id="0f835-112">The \<Tables\> element contains the name of the tables that you add using the plug-in.</span></span> <span data-ttu-id="0f835-113">De forma similar, el \<RFC\> elemento contiene los documentos de RFC que se agregan mediante el complemento.</span><span class="sxs-lookup"><span data-stu-id="0f835-113">Similarly, the \<RFCs\> element contains the RFCs that you add using the plug-in.</span></span> <span data-ttu-id="0f835-114">Si se conecta a más de un servidor SAP, otro \<Server\> elemento se agrega al archivo XML y las tablas correspondientes y RFC aparecen en la \<tabla\> y \<RFC\> elemento.</span><span class="sxs-lookup"><span data-stu-id="0f835-114">If you connect to more than one SAP server, another \<Server\> element is added to the XML file, and the corresponding tables and RFCs are listed under the \<Table\> and \<RFCs\> element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f835-115">Para obtener instrucciones sobre cómo usar el complemento de Visual Studio DDEX, consulte [usa el proveedor de datos para SAP con el complemento DDEX](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="0f835-115">For instructions on using the Visual Studio DDEX plug-in, see [Use the Data Provider for SAP with the DDEX Plug-in](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f835-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f835-116">See Also</span></span>  
 [<span data-ttu-id="0f835-117">Acerca del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="0f835-117">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)