---
title: "Establecer propiedades de transporte TIBCO Enterprise Message Service para el puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, setting transport properties
- transport properties, setting for receive port
- setting transport properties, receive port
ms.assetid: bccddf84-d92e-469f-aa6f-4234c91a0be9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94229364e3bed8faaf1407603f17db76c70e6bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a>Establecimiento de propiedades de transporte de TIBCO Enterprise Message Service para el puerto de recepción
Ubicación de recepción para un sistema TIBCO Enterprise Message (EMS) la **URL** y **Target Namespace** para el sistema TIBCO EMS son los únicos valores de configuración necesarios.  
  
### <a name="to-specify-tibco-ems-transport-properties"></a>Para especificar propiedades de transporte de TIBCO EMS  
  
1.  Expanda el **definición del sistema** y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.  
  
2.  Expanda **control de mensajes** y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**Selector de mensajes**|Los mensajes únicamente se reciben si esta cadena se evalúa en True con el mensaje en el destino.<br /><br /> Permite que el puerto de recepción recupere únicamente los mensajes que contienen propiedades de encabezado que coincidan con la expresión descrita en este campo.<br /><br /> La sintaxis de los selectores de mensajes se basa en un subconjunto de la sintaxis de expresiones condicionales de SQL92. La sintaxis se describe completamente en la guía del usuario de TIBCO EMS.<br /><br /> Por ejemplo, si un mensaje contiene un nombre de propiedad de encabezado NewsType, un puerto de recepción únicamente puede recuperar los elementos que sean de tipo Sports o Editorial.|  
    |**Número de reintentos**|El número de reintentos para el transporte. Valor predeterminado es 0.|  
    |**Intervalo de reintento**|El período de tiempo que el adaptador espera antes de iniciar un reintento. El valor predeterminado es cinco minutos.|  
  
3.  Expanda el **definición de conexión de servidor** y escriba toda la información necesaria.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**Destino**|Configuración obligatoria. Define el nombre y tipo de destino. Define la cola o tema con el formato siguiente: Queue[queue.name] o Topic[topic.name].|  
    |**Número de puerto**|Puerto en que escucha el servidor TIBCO EMS.|  
    |**Nombre de servidor**|Configuración obligatoria. Nombre del sistema que hospeda el servidor TIBCO EMS.|  
  
4.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Se pueden usar dos métodos para tener acceso al sistema TIBCO EMS. Puede usar las credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    -   Seleccione **Sí** en **usar SSO** usar Single Sign-On.  
  
    -   Seleccione una aplicación afiliada en la lista.  
  
         Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS. El adaptador de Microsoft BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
         Para obtener más información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).  
  
5.  Expanda **las credenciales de usuario** y escriba la **nombre de usuario** y **contraseña** para tener acceso al servidor TIBCO EMS.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |`Password`|La contraseña del usuario que se usa para comunicar con un demonio TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
    |`User Name`|Nombre de un usuario que se usa para comunicar con un demonio TIBCO EMS.<br /><br /> Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.|  
  
6.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación de puertos de envío](../core/creating-send-ports1.md)   
 [Creación de TIBCO Enterprise Message Service controladores de recepción](../core/creating-tibco-enterprise-message-service-receive-handlers.md)