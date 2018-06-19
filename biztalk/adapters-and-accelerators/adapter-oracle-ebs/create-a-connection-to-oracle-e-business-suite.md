---
title: Crear una conexión a Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeeab604-155e-4806-b77a-45319a3f8cc0
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ffdfdc8810024e331598211529f3a594e0169f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216580"
---
# <a name="create-a-connection-to-oracle-e-business-suite"></a>Crear una conexión a Oracle E-Business Suite
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, habilita la comunicación con Oracle E-Business Suite a través de una dirección de extremo WCF. En WCF, la dirección del extremo identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se utiliza para establecer una conexión a Oracle E-Business Suite. Debe especificar un URI de conexión al que:  
  
-   Crear un generador de canales o un agente de escucha del canal mediante el modelo de canal WCF o cuando se crea un host de servicio o cliente WCF mediante el modelo de servicio WCF.  
  
-   Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para una solución de BizTalk Server.  
  
-   Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  

## <a name="ways-to-connect-to-oracle"></a>Métodos para conectarse a Oracle  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite dos formas de establecer una conexión con la base de datos de Oracle subyacente:  
  
-   **Usar tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene solo el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, nombre de servicio, número de puerto y así sucesivamente, de la entrada de nombre de servicio de red en el archivo. Para utilizar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
    > [!IMPORTANT]
    >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md) no puede contener más de 39 caracteres si está realizar operaciones en una transacción. Por lo tanto, si va a realizar las operaciones en una transacción, asegúrese de que el **DataSourceName** valor del parámetro es menor o igual a 39 caracteres.  
  
-   **Sin usar tnsnames.ora**. En este enfoque, los clientes de adaptador escriba los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red que esté presente en el archivo tnsnames.ora en el equipo cliente. Este enfoque no requiere incluso el archivo tnsnames.ora debe estar presente en el equipo cliente.  
  
    > [!IMPORTANT]
    >  No se admite este modo de conectividad si va a realizar las operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  

## <a name="in-this-section"></a>En esta sección    
 Los temas siguientes describen cómo establecer una conexión entre el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y Oracle E-Business Suite:  
  
-   [Configurar el cliente de Oracle para el adaptador de E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md): información sobre el uso de tnsnames.ora a cconfiguring el cliente de Oracle (necesario solo si se usa el tnsnames.ora para establecer la conexión)  
  
-   [Crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md): obtener información acerca de las propiedades de conexión y la estructura de lo URI de conexión de Oracle E-Business Suite
  
-   [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md): obtener información sobre cómo conectarse a Oracle mediante la autenticación de Windows
  