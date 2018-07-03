---
title: Conectarse a la base de datos de Oracle en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 766264c8-bb3f-49e9-b851-1022d1fa5076
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 999c7b369f20bf0871e1150ddddd8dff977afa35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013909"
---
# <a name="connect-to-oracle-database-in-visual-studio"></a>Conectarse a la base de datos de Oracle en Visual Studio
Cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

## <a name="connection-options-in-visual-studio"></a>Opciones de conexión de Visual Studio

Cuando se usa [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)], hay varias opciones disponibles para conectarse a la base de datos de Oracle. Estas opciones incluyen: 

- El **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de BizTalk con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md).  
  
- El **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Usa el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de BizTalk con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md).  
  
  > [!NOTE]
  >  Porque el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a SQL Server.  
  
- El **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones de desarrollo de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
  Para usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], primero debe conectarse a la base de datos de Oracle. Los tres métodos presentan un cuadro de diálogo a través del cual se configura una conexión con la siguiente configuración:  
  
- **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión. Debe especificar un origen de datos (nombre de servicio de red de Oracle).  
  
- **Las credenciales de contraseña de nombre de usuario para la base de datos de Oracle**. Estos se usan para autenticarse en la base de datos de Oracle cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
- **Propiedades de enlace**. Propiedades de enlace son opcionales en tiempo de diseño, es decir, al generar los metadatos para las operaciones. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  
  
  Como mínimo, al configurar la conexión a la base de datos de Oracle, solo tiene que especificar las propiedades de enlace y los parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones desea tener como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
- El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y los parámetros de conexión que especifique al configurar la conexión y este archivo se agrega al proyecto. Más adelante, puede usar este archivo de enlace para crear un puerto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información sobre el archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
- El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config desde las propiedades de enlace y las propiedades de conexión que especifique al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  

  
## <a name="see-also"></a>Vea también  
[Obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)