---
title: Procedimientos recomendados para proteger el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security best practices, for consuming the Siebel adapter with BizTalk Server
- security best practices, for connection between the Siebel adapter and Siebel system
- best practices, security
- security, best practices
- security best practices, for hosting the Siebel adapter in IIS
- security best practices, for WCF diagnostic tracing and message logging
- security best practices, for consuming the Siebel adapter with programming solutions
ms.assetid: da89fcc5-2705-4198-8df6-64b2c532ef41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0dadf9407bfbe3b672975e90e2a63c589292b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004165"
---
# <a name="best-practices-to-secure-the-siebel-adapter"></a>Procedimientos recomendados para proteger el adaptador de Siebel
Esta sección proporciona procedimientos recomendados que debe seguir para proteger información confidencial más completamente cuando se utiliza o desarrollar aplicaciones que consumen el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
## <a name="security-best-practices-for-the-connection-between-the-siebel-adapter-and-the-siebel-system"></a>Prácticas recomendadas de seguridad para la conexión entre el adaptador de Siebel y el sistema Siebel  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite el cifrado mscrypto o rsa en los datos intercambiados entre el adaptador y el sistema Siebel. Para ayudar a garantizar la privacidad de los datos que se intercambian entre el adaptador y el sistema de Siebel, debe habilitar uno de estos modos de cifrado.  
  
- El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no proporciona mecanismos para ayudar a garantizar la integridad de los datos o para proporcionar autenticación y autorización en los datos que se intercambian entre ella y el sistema Siebel. Debe proporcionar mecanismos, si existen estas preocupaciones en su entorno.  
  
- No proporciona credenciales de contraseña del nombre de usuario para el sistema Siebel en el URI de conexión. Vea el resto de este tema para obtener métodos alternativos de proporcionar credenciales para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
  Para obtener más información, consulte [seguridad entre Siebel y el adaptador](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
## <a name="security-best-practices-for-consuming-the-siebel-adapter-with-biztalk-server"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de Siebel con BizTalk Server  
  
- No proporciona credenciales de contraseña del nombre de usuario para el sistema Siebel en el URI de conexión.  
  
- Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], escriba las credenciales de contraseña del nombre de usuario para el sistema Siebel desde el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
- Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en un puerto de envío, escriba las credenciales de contraseña del nombre de usuario para el sistema Siebel desde el **credenciales** pestaña de la **Configurar transporte personalizado de WCF**  cuadro de diálogo.  
  
- Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en una ubicación de recepción, escriba las credenciales de contraseña del nombre de usuario para el sistema Siebel desde el **otros** pestaña de la **Configurar transporte personalizado de WCF**  cuadro de diálogo.  
  
  Para obtener más información, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
## <a name="security-best-practices-for-consuming-the-siebel-adapter-with-programming-solutions"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de Siebel con las soluciones de programación  
  
- A veces es necesario proporcionar al usuario las credenciales de contraseña de nombre para el sistema Siebel en la conexión URI; Sin embargo, si es posible, debe evitar hacerlo.  
  
- Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], escriba las credenciales de contraseña del nombre de usuario para el sistema Siebel desde el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
- En la programación del modelo de canal de WCF, use el **credenciales** propiedad en el generador de canales para establecer el usuario las credenciales de contraseña de nombre para el sistema Siebel.  
  
- En la programación del modelo de servicio WCF, use el **ClientCredentials** propiedad en el cliente WCF para establecer el usuario las credenciales de contraseña de nombre para el sistema Siebel.  
  
- Si una aplicación que consume el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, asegúrese de que estos mensajes tienen suficientes medidas de seguridad que se aplica para proporcionar los datos adecuados protección de su entorno.  
  
  Para obtener más información, vea [programación segura con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md) 
  
## <a name="security-best-practices-for-hosting-the-siebel-adapter-in-iis"></a>Prácticas recomendadas de seguridad para hospedar el adaptador de Siebel en IIS  
  
- Hospedar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en Microsoft Internet Information Services (IIS) como un sitio Web de servicio expone las operaciones obtenidas por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a los clientes Web. Estas operaciones pueden implicar intercambiar datos confidenciales a través de Internet, por lo que debe tomar medidas para ayudar a garantizar que estos datos están tan seguros como sea posible.  
  
   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona dos enlaces estándares para el transporte HTTP: el **BasicHttpBinding** proporciona el transporte HTTP básica con ningún mecanismo de seguridad; el **WSHttpBinding** admite ambos nivel de transporte y mecanismos de seguridad de nivel de mensaje.  
  
   Puede usar el **BasicHttpBinding** a través de una conexión HTTPS o use el **WSHttpBinding** para ayudar a proteger los datos. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] incluye el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para generar servicios WCF para artefactos de LOB. Este asistente sólo admite el uso de **BasicHttpBinding**.  
  
   También puede desarrollar un enlace HTTP personalizado para aprovechar los mecanismos de seguridad adicional que proporciona el entorno. Para obtener más información acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [proteger servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx).
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>Prácticas recomendadas de seguridad para el seguimiento de diagnóstico de WCF y el registro de mensajes  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] admite el seguimiento de diagnóstico y registro de mensajes. Configurar el seguimiento de diagnóstico y registro de mensajes a través de los archivos de configuración o mediante el uso de Windows Management Instrumentation (WMI). Dependiendo de las opciones de configuración se establece, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] seguimiento de diagnóstico o mensaje de registro puede emitir información confidencial para registrar los archivos, donde potencialmente están expuesta a observación por los usuarios no autorizados.  
  
 Siga las recomendaciones proporcionadas en la documentación de WCF para mitigar posibles amenazas de seguridad que se muestran cuando se habilita estas características. Como mínimo, debería observar las siguientes prácticas recomendadas para el seguimiento de diagnóstico y registro de mensajes:  
  
- No habilite "detallado" o seguimiento de "información" en un entorno de producción. Esto puede provocar una degradación del rendimiento. Sin embargo, debe habilitar "Advertencia" y el seguimiento de "error" en un entorno de producción. Si habilita el seguimiento, debe tomar medidas de seguridad adecuadas para proteger los datos. Consulte la documentación de WCF para obtener más información.  
  
- Asegúrese de que los archivos de registro y archivos de configuración están protegidos por listas de control de acceso (ACL).  
  
  Las advertencias siguientes se aplican específicamente a los mensajes que se intercambian entre una aplicación cliente y el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]:  
  
- [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] seguimiento de diagnóstico puede iniciar el encabezado (pero no el cuerpo) de los mensajes intercambiados con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Dado que la acción del mensaje está en el encabezado del mensaje, esto revelan las operaciones invocadas en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] por el cliente.  
  
- Si [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] está habilitado el registro de mensajes y `logMessagesAtServiceLevel` es `true`, el encabezado del mensaje (pero no el cuerpo del mensaje) de los mensajes intercambiados entre el cliente del adaptador y el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se registran. Dado que la acción del mensaje está en el encabezado del mensaje, esto revelan las operaciones que el cliente se invoca en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Si `logEntireMessage` también es `true`, se registrará el cuerpo del mensaje. Esto puede revelar información confidencial de la base de datos.  
  
  Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita la traza de diagnóstico, consulte [cuestiones de seguridad y sugerencias útiles para el seguimiento](https://msdn.microsoft.com/library/ms733053.aspx). Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita el registro de mensajes, vea [cuestiones de seguridad para el registro de mensajes](https://msdn.microsoft.com/library/ms730318.aspx).
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)