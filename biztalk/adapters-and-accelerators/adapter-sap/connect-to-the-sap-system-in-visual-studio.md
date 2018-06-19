---
title: Conectarse al sistema SAP en Visual Studio | Documentos de Microsoft
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
ms.openlocfilehash: 20cd25c327f2081fed61e19e1571b91a0e39f556
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22217788"
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>Conectarse al sistema SAP en Visual Studio
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   El **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** está disponible en proyectos de BizTalk Server. Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones SAP desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
-   El **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** está disponible en proyectos de BizTalk Server. Utiliza el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones SAP desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
    > [!NOTE]
    >  Dado que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede utilizar cualquiera el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a un sistema SAP.  
  
-   El **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones SAP desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
 Para usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] primero debe conectarse al sistema SAP. Toda la interfaz de usuario de tres presentar un cuadro de diálogo a través del cual configurar una conexión con la siguiente configuración:  
  
-   **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión como host de servidor de aplicación o el host de servidor de mensaje e identificador de cliente.  
  
-   **Las credenciales de contraseña del nombre de usuario para el sistema SAP**. Estos se utilizan para autenticarle en el sistema SAP cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
-   **Propiedades de enlace**. Propiedades de enlace son opcionales y no se especifique depende principalmente de si elige como destino las operaciones que requieren establecer las propiedades de enlace concreto. Por ejemplo, para una operación de ReceiveIdoc debe establecer el **ReceiveIdocFormat** enlaza la propiedad de cadena. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Como mínimo, al configurar la conexión con el sistema SAP, basta con especificar propiedades de enlace y parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para las operaciones desee establecer como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
-   El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y parámetros de conexión que especifique al configurar la conexión y agrega este archivo al proyecto.  
  
-   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y propiedades de conexión que especifique al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  

  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)