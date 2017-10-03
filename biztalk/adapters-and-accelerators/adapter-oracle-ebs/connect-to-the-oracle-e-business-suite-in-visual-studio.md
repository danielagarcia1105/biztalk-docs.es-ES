---
title: Conectarse a Oracle E-Business Suite en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e290ea7e-03f3-49d4-9f18-1e539d727d9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9221914a9f58c3f739eefd5f07986b0105f77e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-oracle-e-business-suite-in-visual-studio"></a>Conectarse a Oracle E-Business Suite en Visual Studio
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   El  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
-   El  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Utiliza el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
    > [!NOTE]
    >  Dado que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede utilizar cualquiera el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a Oracle E-Business Suite.  
  
-   El  **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**  está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones desarrollar Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md).  
  
 Para usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], primero debe conectarse a Oracle E-Business Suite. Los tres métodos proporciona un cuadro de diálogo a través del cual configurar una conexión con la siguiente configuración:  
  
-   **Parámetros de conexión**. Estos son los parámetros que se utilizan para generar el URI de conexión. Debe especificar un origen de datos (nombre de servicio de red de Oracle).  
  
-   **Las credenciales de contraseña del nombre de usuario para Oracle E-Business Suite**. Estos se utilizan para autenticarle en Oracle E-Business Suite cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
    > [!IMPORTANT]
    >  En esta fase, puede especificar las credenciales para Oracle E-Business Suite o la base de datos de Oracle subyacente. Puede especificar las credenciales para conectarse y generar los metadatos. Sin embargo, al realizar la operación para invocar un artefacto de Oracle E-Business Suite, debe especificar las credenciales de Oracle E-Business Suite porque son necesarias para establecer el contexto de la aplicación para la aplicación de Oracle E-Business Suite que se va a invocar. Para obtener más información sobre el contexto de las aplicaciones de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
-   **Propiedades de enlace**. Propiedades de enlace son opcionales en tiempo de diseño, es decir, al generar metadatos para las operaciones. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 Como mínimo, al configurar la conexión a la base de datos de Oracle, basta con especificar propiedades de enlace y parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones desea tener como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
-   El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y parámetros de conexión que se especifican al configurar la conexión y agrega este archivo al proyecto. Posteriormente, puede utilizar este archivo de enlace para crear un puerto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información sobre el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
-   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y propiedades de conexión que se especifican al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  

-   [Conectarse a Oracle E-Business Suite en Visual Studio con agregar un complemento de referencia de servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-service-reference.md)  
  
## <a name="see-also"></a>Vea también  
 [Obtiene los metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)