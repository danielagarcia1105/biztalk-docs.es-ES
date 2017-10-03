---
title: Conectarse a la base de datos de Oracle en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 766264c8-bb3f-49e9-b851-1022d1fa5076
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1c0bd45e311a2d6b56fdda9560a1c0300bb711b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-in-visual-studio"></a>Conectarse a la base de datos de Oracle en Visual Studio
Cómo utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

## <a name="connection-options-in-visual-studio"></a>Opciones de conexión en Visual Studio

Cuando se usa [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)], hay varias opciones disponibles para conectarse a la base de datos de Oracle. Estas opciones incluyen: 

-   El  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md).  
  
-   El  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Utiliza el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md).  
  
    > [!NOTE]
    >  Dado que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede utilizar cualquiera el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a SQL Server.  
  
-   El  **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**  está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones de desarrollar bases de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
 Para usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], primero debe conectarse a la base de datos de Oracle. Los tres métodos proporciona un cuadro de diálogo a través del cual configurar una conexión con la siguiente configuración:  
  
-   **Parámetros de conexión**. Estos son los parámetros que se utilizan para generar el URI de conexión. Debe especificar un origen de datos (nombre de servicio de red de Oracle).  
  
-   **Las credenciales de contraseña del nombre de usuario para la base de datos de Oracle**. Estos se utilizan para la autenticación, en la base de datos de Oracle cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
-   **Propiedades de enlace**. Propiedades de enlace son opcionales en tiempo de diseño, es decir, al generar metadatos para las operaciones. Para obtener más información acerca de las propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
 Como mínimo, al configurar la conexión a la base de datos de Oracle, basta con especificar propiedades de enlace y parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones desea tener como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
-   El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y parámetros de conexión que se especifican al configurar la conexión y agrega este archivo al proyecto. Posteriormente, puede utilizar este archivo de enlace para crear un puerto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información sobre el archivo de enlace, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
-   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y propiedades de conexión que se especifican al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  

  
## <a name="see-also"></a>Vea también  
[Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)