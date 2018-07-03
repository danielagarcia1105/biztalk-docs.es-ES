---
title: Crear una conexión a la base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: c79af51280879e1cf6c72053a42822cd24fae68e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988461"
---
# <a name="create-a-connection-to-the-oracle-database"></a>Crear una conexión a la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, permite la comunicación a una base de datos de Oracle a través de una dirección de extremo WCF. En WCF, la dirección de punto de conexión se expresa normalmente como de un identificador de recursos uniforme (URI), que identifica la ubicación de red del servicio. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza para establecer una conexión a la base de datos de Oracle.  
  
 Debe especificar un URI de conexión cuando le:  
  
- Crear un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal o al crear un host de servicio o cliente WCF mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
- Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite dos formas de establecer una conexión a la base de datos de Oracle:  
  
- **Uso de tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene únicamente el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, nombre de servicio, número de puerto, etc., de la entrada del nombre de servicio de red en el archivo. Para usar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
  > [!IMPORTANT]
  >  Debido a una limitación del cliente de Oracle, el **DataSourceName** parámetro (nombre de servicio de red) en el [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) no puede contener más de 39 caracteres si va a realizar operaciones en una transacción. Por lo tanto, asegúrese de que el valor especificado para el **DataSourceName** parámetro es menor o igual a 39 caracteres si va a realizar operaciones en una transacción.  
  
- **Sin usar tnsnames.ora**. En este enfoque, los clientes del adaptador especifican los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red esté presente en el archivo tnsnames.ora en el equipo cliente. Incluso este enfoque no requiere el archivo tnsname.ora debe estar presente en el equipo cliente.  
  
  > [!IMPORTANT]
  >  No se admite este modo de conectividad si va a realizar operaciones en una transacción. Esto es debido a una limitación del cliente de Oracle.  
  
  Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] y la base de datos de Oracle, ya que con:  
  
- Información sobre cómo configurar al cliente de Oracle.  
  
- Información sobre las propiedades de conexión y la estructura de lo URI de conexión de Oracle.  
  
- Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
- Información sobre cómo conectarse a la base de datos de Oracle mediante la autenticación de Windows.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar al cliente de Oracle para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [Crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [Conectarse a la base de datos de Oracle mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)