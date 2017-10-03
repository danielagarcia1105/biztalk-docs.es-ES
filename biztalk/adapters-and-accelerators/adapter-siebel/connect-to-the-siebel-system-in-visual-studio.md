---
title: Conectarse al sistema Siebel en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Adapter Service Reference Plug-in
- Consume Adapter Service Add-in
- how to, connect to the Siebel System in Visual Studio
ms.assetid: 4a94bce9-fda9-4e00-b26c-08672a80e3be
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f7bacf42f90da21830d24587cc7ae6a6e042bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio"></a>Conectarse al sistema Siebel en Visual Studio
Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   El  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [aplicaciones de BizTalk de desarrollar con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).  
  
-   El  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  está disponible en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] instalación. Utiliza el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [aplicaciones de BizTalk de desarrollar con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).  
  
    > [!NOTE]
    >  Dado que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede utilizar cualquiera el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a un sistema Siebel.  
  
-   El  **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**  está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones Siebel desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).  
  
 Para usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], primero debe conectarse al sistema Siebel. Los tres métodos proporciona un cuadro de diálogo a través del cual configurar una conexión con la siguiente configuración:  
  
-   **Parámetros de conexión**. Estos son los parámetros que se utilizan para generar el URI de conexión, como el nombre del servidor de empresa de Siebel.  
  
-   **Las credenciales de contraseña del nombre de usuario para el sistema Siebel**. Estos se utilizan para autenticarle en el sistema Siebel cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
-   **Propiedades de enlace**. Propiedades de enlace son opcionales y no se especifique depende principalmente de si elige como destino las operaciones que requieren establecer las propiedades de enlace concreto.  
  
 Como mínimo, al configurar la conexión con el sistema Siebel, basta con especificar propiedades de enlace y parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para las operaciones desee establecer como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
-   El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y parámetros de conexión que especifique al configurar la conexión y agrega este archivo al proyecto.  
  
-   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y propiedades de conexión que especifique al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  
 
  
## <a name="see-also"></a>Vea también  
 [Obtiene los metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)