---
title: Conectarse a Oracle E-Business Suite en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e290ea7e-03f3-49d4-9f18-1e539d727d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3be6f861e2346b4cc7d8ad29598d8efbc4707c76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984277"
---
# <a name="connect-to-the-oracle-e-business-suite-in-visual-studio"></a>Conectarse a Oracle E-Business Suite en Visual Studio
Esta sección proporciona información sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- El **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
- El **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos. Usa el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
  > [!NOTE]
  >  Porque el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a Oracle E-Business Suite.  
  
- El **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones de desarrollo de Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md).  
  
  Para usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], primero debe conectarse a Oracle E-Business Suite. Los tres métodos presentan un cuadro de diálogo a través del cual se configura una conexión con la siguiente configuración:  
  
- **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión. Debe especificar un origen de datos (nombre de servicio de red de Oracle).  
  
- **Las credenciales de contraseña del nombre de usuario para Oracle E-Business Suite**. Estos se usan para autenticarse en Oracle E-Business Suite cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
  > [!IMPORTANT]
  >  En esta fase, puede especificar las credenciales para Oracle E-Business Suite o la base de datos de Oracle subyacente. Puede especificar las credenciales para conectarse y generar los metadatos. Sin embargo, al realizar la operación para invocar un artefacto de Oracle E-Business Suite, debe especificar las credenciales de Oracle E-Business Suite porque son necesarias para establecer el contexto de la aplicación para la aplicación de Oracle E-Business Suite que desea invocar. Para obtener más información acerca del contexto de las aplicaciones de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
- **Propiedades de enlace**. Propiedades de enlace son opcionales en tiempo de diseño, es decir, al generar los metadatos para las operaciones. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
  Como mínimo, al configurar la conexión a la base de datos de Oracle, solo tiene que especificar las propiedades de enlace y los parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para las operaciones desea tener como destino. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
- El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y los parámetros de conexión que especifique al configurar la conexión y este archivo se agrega al proyecto. Más adelante, puede usar este archivo de enlace para crear un puerto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener más información sobre el archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).  
  
- El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config desde las propiedades de enlace y las propiedades de conexión que especifique al configurar la conexión y agrega este archivo en el directorio del proyecto.  
  

- [Conectarse a Oracle E-Business Suite en Visual Studio mediante el complemento Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-service-reference.md)  
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)