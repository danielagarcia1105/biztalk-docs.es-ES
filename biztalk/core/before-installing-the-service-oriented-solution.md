---
title: "Antes de instalar el servicio de la solución orientada a servicios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7e611996e58291cdf6ed5d6b38b2b2fe5c299d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="before-installing-the-service-oriented-solution"></a>Antes de instalar la solución orientada a servicios
Para instalar la versión de código auxiliar de la solución orientada a servicios en un único equipo, éste debe reunir los siguientes requisitos previos:  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].  
  
-   Software compatible para [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].  
  
-   La última versión del cliente IBM WebSphere MQ para Windows  
  
    > [!NOTE]
    >  Para la versión de código auxiliar de la solución no se necesita MQSeries.  
  
    > [!NOTE]
    >  Puede descargar el cliente IBM WebSphere MQ para Windows desde el sitio Web de IBM.  
  
 Para instalar las versiones de adaptador y en línea de la solución orientada a servicios en un único equipo:  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].  
  
    > [!NOTE]
    >  Necesita una cuenta de dominio para asignar credenciales para el inicio de sesión único (SSO) empresarial. Se recomienda utilizar cuentas de dominio para el servicio de BizTalk y para las cuentas de servicio ENTSSO.  
  
-   Software compatible para [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].  
  
-   MQSeries Server en el equipo local o acceso al equipo en el que se ejecuta. Para la versión en línea, las API de cliente de MQSeries deben estar disponibles en el servidor que ejecuta las orquestaciones de la solución.  
  
    > [!NOTE]
    >  La versión de MQSeries Server debe coincidir con la versión que requiere el Adaptador de MQSeries para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]. Esto puede incluir IBM WebSphere MQ para Windows, versión 5.3, con Fix Pack 10 (CSD10) o posterior.  
  
    > [!NOTE]
    >  Cuando se usan características como MQSeries que hacen llamadas del Modelo de objetos componentes distribuido (DCOM) al servidor, asegúrese de que no tiene un servidor de seguridad con NAT (Traducción de direcciones de red) habilitado. El cliente debe poder obtener acceso al servidor mediante su dirección IP real y los servidores de seguridad con NAT traducen esta dirección en algo que el cliente no reconoce.  
  
-   Si va a utilizar una variación de la solución que requiere un gran sistema (mainframe), necesitará IBM Mainframe con CICS y Transaction X. En este caso, hay que instalar la aplicación CICS (código COBOL) en el gran sistema y necesitará Microsoft Host Integration Server (HIS) para obtener acceso al mismo.  
  
     Si la solución no requiere un gran sistema, puede modificar el enlace de puertos para utilizar el servicio Web de código auxiliar para las transacciones pendientes.. El servicio Web genera transacciones localmente para emular las transacciones de gran sistema. Para obtener más información acerca de cómo modificar el enlace de puerto para el servicio Web de transacciones pendientes de código auxiliar, vea [cómo instalar las versiones de adaptador de la solución orientada a servicios y en línea](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).  
  
-   Se requiere Host Integration Server para conectarse al gran sistema.  
  
    > [!NOTE]
    >  Host Integration Server se incluye como parte de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
-   Un servidor Web configurado con un certificado para realizar conexiones HTTPS.  
  
## <a name="see-also"></a>Vea también  
 [Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [Cómo ejecutar el servicio de la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md)   
 [Solución orientada a servicios de configuración del equipo del desarrollador para el servicio](../core/developer-machine-setup-for-the-service-oriented-solution.md)