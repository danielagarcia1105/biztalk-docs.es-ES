---
title: Acerca del archivo de SAPDiscoveredObjects.xml en SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDiscoveredObjects.xml
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- Visual Studio DDEX plug-in
ms.assetid: 46ef600d-57ae-4c42-94ce-3099e42482f1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba0c156e2ad6ab0fcbccb5ba7629f63b0aa490e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960722"
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a>Acerca del archivo de SAPDiscoveredObjects.xml en SAP
Si decide instalar la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, el programa de instalación copia el archivo SAPDiscoveredObjects.xml normalmente en \<unidad de instalación\>: \Program Files\Common archivos \Microsoft Shared\Adapters\SAP. El contenido del archivo, después de una instalación nueva de la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], similares a los siguientes.  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 El propósito del archivo SAPDiscoveredObjects.xml es almacenar los objetos SAP (tablas y RFC) que detectan mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] complemento DDEX. Una vez que ha usado el complemento DDEX para agregar más objetos SAP, se agregan a este archivo XML. El archivo XML tiene el siguiente aspecto.  
  
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
  
 El `name` propiedad de la < servidor\> elemento contiene el nombre del servidor que se conecta a mediante el complemento DDEX. El `user` y `client` propiedades de la < servidor\> elemento contienen los números de cliente y el nombre de usuario, respectivamente. El `type` propiedad contiene el tipo de cadena de conexión utilizada para conectarse a un sistema SAP (A, B o D). Para obtener más información acerca de los tipos de cadenas de conexión, vea [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).  
  
 El \<tablas\> elemento contiene el nombre de las tablas que se agregan mediante el complemento. De forma similar, el \<RFC\> elemento contiene los documentos de RFC que se agregan mediante el complemento. Si se conecta a más de un servidor SAP, otro \<Server\> elemento se agrega al archivo XML y las tablas correspondientes y RFC aparecen en la \<tabla\> y \<RFC\> elemento.  
  
> [!NOTE]
>  Para obtener instrucciones sobre cómo usar el complemento de Visual Studio DDEX, consulte [usa el proveedor de datos para SAP con el complemento DDEX](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md).  
  
## <a name="see-also"></a>Vea también  
 [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)