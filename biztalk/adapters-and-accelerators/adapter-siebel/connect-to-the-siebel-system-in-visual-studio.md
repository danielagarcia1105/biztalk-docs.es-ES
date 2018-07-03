---
title: Conectarse al sistema Siebel en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add Adapter Service Reference Plug-in
- Consume Adapter Service Add-in
- how to, connect to the Siebel System in Visual Studio
ms.assetid: 4a94bce9-fda9-4e00-b26c-08672a80e3be
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 064382776201ec6772cc4864c153731ab8c11989
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999741"
---
# <a name="connect-to-the-siebel-system-in-visual-studio"></a>Conectarse al sistema Siebel en Visual Studio
Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- El **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** está disponible en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [aplicaciones de desarrollo de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).  
  
- El **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** está disponible en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos y se instala como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] instalación. Usa el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [aplicaciones de desarrollo de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).  
  
  > [!NOTE]
  >  Porque el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se expone como un enlace WCF-Custom y como el adaptador de BizTalk, puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] desde un proyecto de BizTalk para conectarse a un sistema Siebel.  
  
- El **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [Siebel desarrollar las aplicaciones mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).  
  
  Para usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], o el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], primero debe conectarse al sistema Siebel. Los tres métodos presentan un cuadro de diálogo a través del cual se configura una conexión con la siguiente configuración:  
  
- **Parámetros de conexión**. Estos son los parámetros que se usan para generar el URI de conexión, como el nombre del servidor de empresa de Siebel.  
  
- **Las credenciales de contraseña del nombre de usuario para el sistema Siebel**. Estos se usan para autenticarse en el sistema Siebel cuando se establece la conexión. Debe especificar un nombre de usuario y una contraseña.  
  
- **Propiedades de enlace**. Propiedades de enlace son opcionales y si especificarlos depende principalmente de si elige como destino las operaciones que requieren establecer las propiedades de enlace concreto.  
  
  Como mínimo, al configurar la conexión al sistema Siebel, solo tiene que especificar las propiedades de enlace y los parámetros de conexión que son necesarios para establecer la conexión y que afectan a los metadatos devueltos por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para las operaciones ¿desea dirigirse. Sin embargo, también puede especificar valores para las propiedades de enlace adicionales y parámetros de conexión que se usará en tiempo de ejecución. Esto es porque:  
  
- El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] crea un archivo de enlace de puerto de BizTalk a partir de las propiedades de enlace y los parámetros de conexión que especifique cuando configure la conexión y este archivo se agrega al proyecto.  
  
- El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] crea un archivo app.config a partir de las propiedades de enlace y las propiedades de conexión que especifique cuando configure la conexión y agrega este archivo en el directorio del proyecto.  
  
 
  
## <a name="see-also"></a>Vea también  
 [Obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)