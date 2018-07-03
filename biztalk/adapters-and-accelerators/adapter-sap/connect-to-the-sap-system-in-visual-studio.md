---
title: Conectarse al sistema SAP en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- Add Adapter Service Reference Visual Studio Plug-in
- Consume Adapter Service BizTalk Project Add-in
ms.assetid: 5fc356b1-05e8-4235-bb04-5ef6192c5291
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93acb23887eb173f924d21668077454718aa0145
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982909"
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>Conectarse al sistema SAP en Visual Studio
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- El **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** está disponible en proyectos de BizTalk Server. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
- El **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** está disponible en proyectos de BizTalk Server. Usa el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
  > [!NOTE]
  >  Porque el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a un sistema SAP.  
  
- El **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones de desarrollo de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
  Para usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] primero debe conectarse al sistema SAP. Toda la interfaz de usuario tres presente un cuadro de diálogo a través del cual se configura una conexión con la siguiente configuración:  
  
- **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión como host de servidor de aplicación o el host del servidor de mensajes e identificador de cliente.  
  
- **Credenciales de contraseña de nombre de usuario para el sistema SAP**. Estos se usan para autenticarse en el sistema SAP cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
- **Propiedades de enlace**. Propiedades de enlace son opcionales y si especificarlos depende principalmente de si elige como destino las operaciones que requieren establecer las propiedades de enlace concreto. Por ejemplo, para una operación ReceiveIdoc debe establecer el **ReceiveIdocFormat** enlaza la propiedad de cadena. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
  Como mínimo, al configurar la conexión al sistema SAP, solo tiene que especificar las propiedades de enlace y los parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para las operaciones ¿desea dirigirse. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
- El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y los parámetros de conexión que especifique cuando configure la conexión y este archivo se agrega al proyecto.  
  
- El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y las propiedades de conexión que especifique cuando configure la conexión y agrega este archivo en el directorio del proyecto.  
  

  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)