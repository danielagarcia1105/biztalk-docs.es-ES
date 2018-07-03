---
title: Crear una conexión a Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: c0da85f6c0968eb7257e980bdbd65a48fcf734f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973309"
---
# <a name="create-a-connection-to-oracle-e-business-suite"></a>Crear una conexión a Oracle E-Business Suite
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, permite la comunicación a Oracle E-Business Suite a través de una dirección de extremo WCF. En WCF, la dirección de punto de conexión identifica la ubicación de red de un servicio y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa para establecer una conexión a Oracle E-Business Suite. Debe especificar un URI de conexión cuando le:  
  
- Crear un generador de canales o un agente de escucha del canal mediante el modelo de canal WCF o al crear un host de servicio o cliente WCF mediante el modelo de servicio WCF.  
  
- Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para una solución de BizTalk Server.  
  
- Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  

## <a name="ways-to-connect-to-oracle"></a>Formas de conectarse a Oracle  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite dos formas de establecer una conexión a la base de datos de Oracle subyacente:  
  
-   **Uso de tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene únicamente el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, nombre de servicio, el número de puerto y así sucesivamente, de la entrada del nombre de servicio de red en el archivo. Para usar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
    > [!IMPORTANT]
    >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md) no puede contener más de 39 caracteres si es realizar operaciones en una transacción. Por lo tanto, si va a realizar operaciones en una transacción, asegúrese de que el **DataSourceName** valor del parámetro es menor o igual a 39 caracteres.  
  
-   **Sin usar tnsnames.ora**. En este enfoque, los clientes del adaptador especifique los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red esté presente en el archivo tnsnames.ora en el equipo cliente. Incluso este enfoque no requiere el archivo tnsnames.ora esté presente en el equipo cliente.  
  
    > [!IMPORTANT]
    >  No se admite este modo de conectividad si va a realizar operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  

## <a name="in-this-section"></a>En esta sección    
 Los temas siguientes describen cómo establecer una conexión entre el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y Oracle E-Business Suite:  
  
-   [Configurar el cliente de Oracle para el adaptador de E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md): información sobre el uso de tnsnames.ora a cconfiguring el cliente de Oracle (necesario solo si se usa el tnsnames.ora para establecer la conexión)  
  
-   [Crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md): información sobre las propiedades de conexión y la estructura de lo URI de conexión de Oracle E-Business Suite
  
-   [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md): información sobre cómo conectarse a Oracle mediante la autenticación de Windows
  