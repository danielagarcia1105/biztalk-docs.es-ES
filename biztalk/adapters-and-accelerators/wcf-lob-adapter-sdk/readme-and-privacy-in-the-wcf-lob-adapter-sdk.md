---
title: Archivo Léame y privacidad en el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 539a88f9-ce59-46e6-8c9a-418484eabff4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0e66bb7f13fd0a7cc39e983ac891708183662b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965170"
---
# <a name="readme-and-privacy-in-the-wcf-lob-adapter-sdk"></a>Archivo Léame y privacidad en el SDK de adaptador LOB de WCF
Línea de Kit de desarrollo de Software (SDK) de negocio (LOB) adaptador de Windows Communication Foundation (WCF)  
  
## <a name="inside-the-sdk"></a>En el SDK  
 En la tabla siguiente muestra el contenido de los distintos componentes de los SDK de adaptador LOB de WCF en el \<carpeta de instalación\> después de la instalación.  
  
|Tipo|Ubicación|Description|  
|----------|--------------|-----------------|  
|Tiempo de ejecución|\<Carpeta de instalación\> \Bin\Microsoft.ServiceModel.Channels.dll<br /><br /> \<Carpeta de instalación\> \Bin\Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse.dll|Estos ensamblados contienen la base incluido el componente de formulario principal que se utiliza dentro de las herramientas de tiempo de ejecución.|  
|Herramientas|\<Carpeta de instalación\> \Tools\Microsoft.ServiceModel.Channels.Tools.PlugInPackage.dll<br /><br /> \<Carpeta de instalación\> \Tools\Microsoft.ServiceModel.Channels.Tools.BizTalkExtension.dll<br /><br /> \<Carpeta de instalación\> \Tools\Microsoft.ServiceModel.Channels.Wizards.dll|**Agregar adaptador servicio referencia complemento de Visual Studio**<br /><br /> (Proyecto de .NET [contextual], agregar referencia de servicio de adaptador)<br /><br /> **Consume Adapter Service complemento del proyecto de BizTalk**<br /><br /> (Proyecto de BizTalk [contextual], agregar, agregar elementos generados, Consume Adapter Service)<br /><br /> **Asistente para desarrollo de adaptador LOB de WCF**<br /><br /> (Archivo, nuevo, proyecto, Visual C#, adaptador LOB de WCF)|  
|Documentación|\<Carpeta de instalación\> \Documents\WCFLOBAdapterSDK.chm|Este archivo incluye contenido conceptual y el contenido de referencia administrada para esta versión.|  
|Archivo de identificador de producto|\<Carpeta de instalación\>\Documents\pid.txt|Este archivo contiene el identificador de producto del SDK de adaptador LOB de WCF. Use este identificador de producto como una referencia al ponerse en contacto con el servicio al cliente de Microsoft y soporte técnico (CSS).|  
|Ejemplos|\<Carpeta de instalación\> \Documents\Samples\ContosoAdapterSample.zip<br /><br /> \<Carpeta de instalación\> \Documents\Samples\EchoAdapterSample.zip|La carpeta de ejemplos contiene dos adaptadores de ejemplo: Contoso adaptador y el eco.|  

## <a name="privacy"></a>Privacidad
Microsoft se compromete a proteger la privacidad de los usuarios finales. Cuando se crea un adaptador mediante [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], puede afectan a la privacidad de sus usuarios finales. Por ejemplo, el adaptador de forma explícita puede recopilar y enviar las credenciales de usuario, o puede enviar y recibir información confidencial de un sistema de línea de negocio. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no envía ninguna información a Microsoft desde su aplicación a menos que el usuario decida enviarla.  
  
### <a name="windows-communication-foundation-privacy"></a>Privacidad de Windows Communication Foundation  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una extensión a la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] y por lo tanto se basa en muchos de los servicios que proporciona. Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] privacidad, consulte [información de privacidad de Windows Communication Foundation](https://msdn.microsoft.com/library/ms733927.aspx).  
  
### <a name="microsoft-wcf-lob-adapter-sdk-privacy"></a>Privacidad SDK de adaptador LOB de WCF de Microsoft  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una API. Como desarrollador, puede proporcionar registro personalizado y capacidades para facilitar la depuración, de seguimiento para la optimización, y auditoría en los adaptadores de crear. Si proporciona capacidades, debe tener en cuenta el tipo de información que registrará y cómo la información estará restringida para que solo autorizadas individuos que tienen acceso. Esto puede incluir lo siguiente:  
  
-   Configuración y el mantenimiento adecuado control listas de acceso (ACL) en archivos de registro y seguimiento.  
  
-   Filtrar datos confidenciales antes de que se escriba en un archivo.  
  
-   Cifrar datos confidenciales antes de que se escriba en un archivo.  