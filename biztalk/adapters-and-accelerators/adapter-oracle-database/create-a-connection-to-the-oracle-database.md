---
title: Crear una conexión a la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f9a42994f0cde9df19e3b80e16fcbafbb2d8d5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-oracle-database"></a>Crear una conexión a la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, habilita la comunicación con una base de datos de Oracle a través de una dirección de extremo WCF. En WCF, la dirección del extremo se expresa normalmente como de un identificador de recursos uniforme (URI), que identifica la ubicación de red del servicio. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se utiliza para establecer una conexión con la base de datos de Oracle.  
  
 Debe especificar un URI de conexión al que:  
  
-   Crear un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal o cuando se crea un host de servicio o cliente WCF con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
-   Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite dos formas de establecer una conexión con la base de datos de Oracle:  
  
-   **Usar tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene solo el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión como nombre del servidor, nombre de servicio, número de puerto, etc. de la entrada de nombre de servicio de red en el archivo. Para utilizar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
    > [!IMPORTANT]
    >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) no puede contener más de 39 caracteres si va a realizar operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para la **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar las operaciones en una transacción.  
  
-   **Sin usar tnsnames.ora**. En este enfoque, los clientes de adaptador especifican los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red que esté presente en el archivo tnsnames.ora en el equipo cliente. Este enfoque no requiere incluso el archivo tnsname.ora debe estar presente en el equipo cliente.  
  
    > [!IMPORTANT]
    >  No se admite este modo de conectividad si va a realizar las operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
 Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y la base de datos de Oracle al proporcionarle con:  
  
-   Información sobre cómo configurar al cliente de Oracle.  
  
-   Información sobre las propiedades de conexión y la estructura del URI de conexión de Oracle.  
  
-   Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   Obtener información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar al cliente de Oracle para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [Crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)