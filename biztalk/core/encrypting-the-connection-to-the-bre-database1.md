---
title: "Cifrar la conexión a la Database1 BRE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63edd2bb-97f1-4b8b-8cdc-f4792909ca86
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd585c596f7635417a4e22cbccda04593e7c598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="encrypting-the-connection-to-the-bre-database"></a>Cifrar la conexión a la base de datos del BRE
Según sea la directiva de seguridad de la empresa, considere la posibilidad de cifrar lo siguiente:  
  
-   Las credenciales transmitidas durante el proceso de inicio de sesión.  
  
-   Los datos transmitidos a través de la red entre el equipo cliente donde se ejecuta la directiva del motor de reglas de negocios (BRE) y la base de datos del motor de reglas.  
  
 En este tema se describe el modo de cifrar las conexiones a las bases de datos del BRE hospedadas en [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] o en [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)].  
  
## <a name="to-encrypt-the-connection-to-the-bre-database-hosted-on-sql-server-2008-sp1-or-sql-server-2008-r2"></a>Para cifrar la conexión a la base de datos de BRE hospedada en SQL Server 2008 SP1 o SQL Server 2008 R2  
 De forma predeterminada, se cifran las credenciales transmitidas durante el proceso de inicio de sesión cuando una aplicación cliente se conecta a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Si no se ha proporcionado ningún certificado al servidor, cuando se inicia, [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] genera un certificado autofirmado que se usa para cifrar los paquetes de inicio de sesión.  
  
 Para habilitar el cifrado de datos que se transmiten a través de una red entre [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y el cliente para una instancia de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], debe establecer el **Forzar cifrado** opción en el servidor a **Sí**o establecer el **Forzar cifrado de protocolo** opción **Sí** en el cliente.  
  
 Cuando el **Forzar cifrado** opción está establecida en **Sí** en el servidor, [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] usa SSL para cifrar toda la comunicación *entre todos los clientes y el servidor de base de datos*. En otras palabras, se cifran todas las conexiones de entrada al servidor. Para habilitar esta opción en el servidor, se recomienda instalar un certificado en el servidor mediante el Administrador de configuración de SQL Server. Si no se instala ningún certificado en el servidor, éste generará automáticamente un certificado autofirmado cuando se inicie la instancia.  
  
 Este certificado autofirmado puede usarse en lugar de un certificado de una entidad emisora de certificados de confianza, pero no proporciona ninguna protección frente a las amenazas de suplantación de identidad. No debe confiar en la SSL con certificados autofirmados en un entorno de producción ni en servidores conectados a Internet. Una vez establecida esta opción, se denegará el acceso a cualquier cliente que no admita el cifrado. SQL Server debe reiniciarse después de establecer el **Forzar cifrado** opción. Puede configurar esta opción mediante el Administrador de configuración de SQL Server (Configuración de red de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]).  
  
 Cuando el **Forzar cifrado de protocolo** se establece en el lado cliente, [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] usa SSL para cifrar toda la comunicación *entre dicho cliente y todos los servidores de*. En otras palabras, se cifran todas las conexiones de salida del cliente. Para habilitar esta opción en el cliente, debe instalar un certificado en el servidor si la **confiar en certificado de servidor** opción en el cliente se establece en **No**. Si el **confiar en certificado de servidor** opción en el cliente se establece en **Sí**, el cliente no valida el certificado de servidor, lo que permite el uso de un certificado autofirmado. Esta opción puede establecerse mediante el Administrador de configuración de SQL Server (Configuración de SQL Native Client).  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]También le permite habilitar el cifrado para una *conexión específica de un cliente al servidor* estableciendo la **Encrypt/Use Encryption for Data** indicador en **Sí** en el cadena de conexión. Sin embargo, el BRE genera automáticamente las cadenas de conexión sin establecer la opción de cifrado en **Sí**. Por tanto, no se puede cifrar una conexión específica con el servidor de base de datos del motor de reglas desde el equipo cliente. En su lugar, debe establecer el **Forzar cifrado de protocolo** opción en el cliente, como se ha mencionado en el párrafo anterior.