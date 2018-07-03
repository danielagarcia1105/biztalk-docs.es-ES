---
title: Cifrar la conexión de base de datos del BRE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63edd2bb-97f1-4b8b-8cdc-f4792909ca86
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a51d2468f31b316a9ab9ac2d8a3fa8ee57f11320
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997701"
---
# <a name="encrypt-the-connection-to-the-bre-database"></a>Cifrar la conexión a la base de datos BRE
Según sea la directiva de seguridad de la empresa, considere la posibilidad de cifrar lo siguiente:  
  
- Las credenciales transmitidas durante el proceso de inicio de sesión.  
  
- Los datos transmitidos a través de la red entre el equipo cliente donde se ejecuta la directiva del motor de reglas de negocios (BRE) y la base de datos del motor de reglas.  
  
  Este tema describe cómo cifrar las conexiones a bases de datos BRE alojadas en SQL Server.  
  
## <a name="encrypt-the-connection-to-the-bre-database"></a>Cifrar la conexión a la base de datos BRE
 De forma predeterminada, se cifran las credenciales transmitidas durante el proceso de inicio de sesión cuando una aplicación cliente se conecta a SQL Server. Si no se ha proporcionado ningún certificado al servidor, cuando se inicia, SQL Server genera un certificado autofirmado que se utiliza para cifrar los paquetes de inicio de sesión.  
  
 Para habilitar el cifrado de datos que se transmiten a través de una red entre SQL Server y el cliente de una instancia de SQL Server, debe establecer el **Forzar cifrado** opción en el servidor a **Sí** o establecer el **Forzar cifrado de protocolo** opción **Sí** en el cliente.  
  
 Cuando el **Forzar cifrado** opción está establecida en **Sí** en el lado del servidor SQL Server usa SSL para cifrar toda comunicación *entre todos los clientes y el servidor de base de datos* . En otras palabras, se cifran todas las conexiones de entrada al servidor. Para habilitar esta opción en el servidor, se recomienda instalar un certificado en el servidor mediante el Administrador de configuración de SQL Server. Si no se instala ningún certificado en el servidor, éste generará automáticamente un certificado autofirmado cuando se inicie la instancia.  
  
 Este certificado autofirmado puede usarse en lugar de un certificado de una entidad emisora de certificados de confianza, pero no proporciona ninguna protección frente a las amenazas de suplantación de identidad. No debe confiar en la SSL con certificados autofirmados en un entorno de producción ni en servidores conectados a Internet. Una vez establecida esta opción, se denegará el acceso a cualquier cliente que no admita el cifrado. SQL Server debe reiniciarse después de establecer el **Forzar cifrado** opción. Puede establecer esta opción mediante el Administrador de configuración de SQL Server (configuración de red de SQL Server).  
  
 Cuando el **Forzar cifrado de protocolo** se establece en el lado cliente, SQL Server utiliza SSL para cifrar toda comunicación *entre dicho cliente y todos los servidores*. En otras palabras, se cifran todas las conexiones de salida del cliente. Para habilitar esta opción en el lado cliente, debe instalar un certificado en el servidor si el **confiar en certificado de servidor** opción en el cliente está establecida en **No**. Si el **confiar en certificado de servidor** opción en el cliente está establecida en **Sí**, el cliente no valida el certificado de servidor, lo que permite el uso de un certificado autofirmado. Esta opción puede establecerse mediante el Administrador de configuración de SQL Server (Configuración de SQL Native Client).  
  
 SQL Server también permite habilitar el cifrado para una *conexión específica de un cliente al servidor* estableciendo el **Encrypt/Use Encryption for Data** marca **Sí** en la cadena de conexión. Sin embargo, el BRE genera automáticamente las cadenas de conexión sin establecer la opción encryption en **Sí**. Por tanto, no se puede cifrar una conexión específica con el servidor de base de datos del motor de reglas desde el equipo cliente. En su lugar, debe establecer el **Forzar cifrado de protocolo** opción en el cliente, como se mencionó en el párrafo anterior.