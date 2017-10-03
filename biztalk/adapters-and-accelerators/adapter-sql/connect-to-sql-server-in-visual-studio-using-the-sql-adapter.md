---
title: Conectarse a SQL Server en Visual Studio mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62fc2c01-6e4d-4b3b-8581-1d57436ef4e9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb5e2d149c9a9533e4bec3c2c1c435bffb3adf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-sql-adapter"></a>Conectarse a SQL Server en Visual Studio mediante el adaptador de SQL
Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   El  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).  
  
-   El  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  está disponible en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] instalación. Utiliza el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [aplicaciones de BizTalk de desarrollar con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).  
  
    > [!NOTE]
    >  Dado que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede utilizar cualquiera el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a SQL Server.  
  
-   El  **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**  está disponible en proyectos de programación no sean de BizTalk. Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones SAP desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
 Para usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], primero debe conectarse a SQL Server. Los tres métodos proporciona un cuadro de diálogo a través del cual configurar una conexión con la siguiente configuración:  
  
-   **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión, como el nombre de SQL Server, el nombre de la instancia de base de datos y el nombre de la base de datos.  
  
-   **Las credenciales de contraseña del nombre de usuario para SQL Server**. Estos se utilizan para autenticarle en SQL Server cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
-   **Propiedades de enlace**. Propiedades de enlace son opcionales y, si se especifica depende principalmente de si elige como destino las operaciones que requieren establecer las propiedades de enlace concreto. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
 Como mínimo, al configurar la conexión a SQL Server, basta con especificar propiedades de enlace y parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para las operaciones que desea destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
-   El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y parámetros de conexión que especifique al configurar la conexión y agrega este archivo al proyecto.  
  
-   El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y propiedades de conexión que especifique al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  
