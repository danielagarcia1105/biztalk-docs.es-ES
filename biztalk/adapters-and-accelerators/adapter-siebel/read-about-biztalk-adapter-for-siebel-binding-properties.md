---
title: Obtener información sobre el adaptador de BizTalk para Siebel propiedades de enlace | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, setting
- binding properties, adapter
- how to, set binding properties
ms.assetid: 48c77a2d-091c-40e0-aaf3-dc2ec34c55f2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3237be098ea19fc7ff35770ddcb38a10d1e85c1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224044"
---
# <a name="read-about-biztalk-adapter-for-siebel-binding-properties"></a>Obtener información sobre el adaptador de BizTalk para Siebel propiedades de enlace
La [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)] expone varias propiedades de enlace que le permiten controlar parte de su comportamiento de tiempo de diseño y tiempo de ejecución. En esta sección se describe estas propiedades de enlace y proporciona vínculos a temas que explican cómo establecerlas.  
  
## <a name="the-siebel-adapter-binding-properties"></a>Las propiedades de enlace del adaptador de Siebel  
 La tabla siguiente muestra la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] propiedades de enlace agrupan por categoría. La categoría hace referencia al nodo en el que cada propiedad de enlace aparece en los cuadros de diálogo que se presentan las diferentes aplicaciones para configurar el adaptador (o enlace).  
  
|Propiedad de enlace|Categoría|Description|Tipo .NET|  
|----------------------|--------------|-----------------|---------------|  
|EnableBizTalkCompatibilityMode|General|Especifica si se debe cargar el elemento de enlace de canal de BizTalk en capas.<br /><br /> Establezca esta propiedad en **True** para cargar el elemento de enlace. En caso contrario, establezca esta propiedad en **False**.<br /><br /> Al usar los adaptadores de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre debe establecer la propiedad en **True**. Al usar los adaptadores de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], siempre debe establecer la propiedad en **False**.|BOOL (System.Boolean)|  
|Nombre|General|Especifica el nombre del archivo generado por la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para contener el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente. El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] forma el nombre de archivo anexando "Cliente" al valor de la **nombre** propiedad el valor predeterminado es "SiebelBinding"; para este valor, el archivo generado se denominarán "SiebelBindingClient".|string|  
|CloseTimeout|General|Especifica el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] tiempo de espera de cierre de la conexión. El valor predeterminado es 1 minuto.|System.DateTime|  
|OpenTimeout|General|Especifica el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] tiempo de espera ha abierto la conexión. El valor predeterminado es 1 minuto.|System.DateTime|  
|ReceiveTimeout|General|Especifica el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] tiempo de espera de recepción de mensajes. El valor predeterminado es 10 minutos.|System.DateTime|  
|SendTimeout|General|Especifica el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] tiempo de espera de envío de mensaje. El valor predeterminado es 1 minuto.|System.DateTime|  
|EnableConnectionPooling|Conexión|Especifica si el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] agrupación de conexiones está habilitada. El valor predeterminado es **true**, que especifica que la agrupación de conexiones está habilitada.|BOOL (System.Boolean)|  
|IdleConnectionTimeout|Conexión|Especifica el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] tiempo de espera de conexión inactiva. Cuando una conexión está inactiva durante un período que supera este tiempo de espera, se eliminará la conexión. El valor predeterminado es 1 minuto.|System.DateTime|  
|MaxConnectionsPerSystem|Conexión|Especifica el número máximo de conexiones en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] agrupación de conexiones. El valor predeterminado es 5. **MaxConnectionsPerSystem** es una propiedad estática dentro de un dominio de aplicación. Esto significa que al cambiar **MaxConnectionsPerSystem** para la instancia de un enlace en un dominio de aplicación, el nuevo valor se aplica a todos los objetos creados a partir de todas las instancias de enlace dentro de ese dominio de aplicación.|int (System.Int32)|  
|EnablePerformanceCounters|Diagnósticos|Especifica si el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] contadores de rendimiento y la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] rendimiento de latencia de LOB contador están habilitados. El valor predeterminado es **true**; se habilitan los contadores de rendimiento. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] contador de rendimiento de latencia de LOB mide el tiempo total que el adaptador se invierte en realizar llamadas al sistema Siebel.|BOOL (System.Boolean)|  
|LogData|Diagnósticos|Especifica si se debe capturar los datos de negocio en los seguimientos. El valor predeterminado es **false**; no se capturan los datos empresariales.|BOOL (System.Boolean)|  
|AcceptCredentialsInUri|No obtenidas por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].|Especifica si el URI de conexión de Siebel puede contener credenciales de usuario para el sistema Siebel. El valor predeterminado es **false**, lo que deshabilita las credenciales de usuario en el URI de conexión. Si **AcceptCredentialsInUri** es **false** y el URI de conexión contiene credenciales de usuario, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce una excepción. Puede establecer **AcceptCredentialsInUri** a **true** si debe especificar las credenciales en el URI. Para obtener más información, consulte [crear la conexión del sistema Siebel URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).|BOOL (System.Boolean)|  
  
## <a name="how-do-i-set-siebel-binding-properties"></a>¿Cómo se puede establecer propiedades de enlace de Siebel?  
 Puede establecer las propiedades de enlace de Siebel al configurar una conexión a un sistema Siebel. Para obtener información acerca de cómo establecer las propiedades de enlace al que:  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).  
  
    > [!IMPORTANT]
    >  Al usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], si no especifica un valor para una propiedad de enlace de tipo cadena y cuyo valor predeterminado es null, a continuación, esa propiedad de enlace no estará disponible en el archivo de enlace (un archivo XML) o el archivo app.config respectivamente. Debe agregar manualmente la propiedad de enlace y su valor en el archivo de enlace o el archivo app.config, si es necesario.  
  
-   Configurar un puerto de envío o recepción (ubicación) del puerto en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).
  
-   Utilizar el modelo de canal WCF en una solución de programación, vea [crear un canal con Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md).  
  
-   Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).  
  
-   Utilice WCF ServiceModel Metadata Utility Tool (svcutil.exe), consulte [mediante la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)