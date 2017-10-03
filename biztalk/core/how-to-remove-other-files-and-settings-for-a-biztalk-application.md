---
title: "Cómo quitar otros archivos y configuraciones para una aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], deleting settings
- managing [applications], deleting files
- undeploying, settings
- applications, undeploying
- undeploying, files
ms.assetid: b947831a-c988-435c-92ec-45f3fd6967de
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9ad98e0f0fc1e65281a1d8195be4f4a708d004f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-other-files-and-settings-for-a-biztalk-application"></a>Cómo quitar otros archivos y configuraciones correspondientes a una aplicación de BizTalk
Este tema describe cómo quitar archivos y la configuración de una aplicación de BizTalk que no puede quitarse cuando se desinstala la aplicación (que se describe en [cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)). Por ejemplo, los certificados, las entradas de Registro COM y COM+, así como los archivos COM no se quitan, a menos que la aplicación incluya un script posterior al procesamiento que los eliminara o los desinstalara.  
  
> [!CAUTION]
>  Antes de quitar algunos elementos compartidos, asegúrese de que ninguna otra aplicación las está usando o las aplicaciones no funcionarán correctamente.  
  
> [!NOTE]
>  Se recomienda que automatice esta eliminación mediante el script posterior al procesamiento. Para obtener más información, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
-   **Eliminar certificados.** Hay dos formas de eliminar certificados del almacén de certificados: mediante la herramienta de línea de comandos Certificate Manager (certmgr.exe) o el complemento Certificados. Certmgr.exe se instala con .NET SDK, que es uno de los requisitos previos de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede ejecutar certmgr.exe de forma manual o puede ejecutarlo desde el script posterior al procesamiento. Para obtener más información acerca del uso de certmgr.exe, vea [herramienta de administrador de certificados (certmgr.exe)](http://go.microsoft.com/fwlink/?LinkId=56198) en el sitio Web de Microsoft.  
  
     El complemento Certificados se incluye en Windows Server 2008 y Windows Vista. Para eliminar un certificado, abra el complemento, tal como se indica en "Iniciar el complemento Certificados" en la Ayuda del sistema operativo y, a continuación, elimine los certificados, como se describe en "Eliminar un certificado" en la Ayuda de Certificados.  
  
-   **Quitar ensamblados desde el registro de Windows.** Para quitar ensamblados .NET y de BizTalk del Registro de Windows, use regsvcs o regasm, que se incluyen con .NET SDK, que es uno de los requisitos previos de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation prerequisites. Para obtener información de referencia, vea [.NET Services Installation Tool (Regsvcs.exe)](http://go.microsoft.com/fwlink/?LinkId=56199) y [Assembly Registration Tool (Regasm.exe)](http://go.microsoft.com/fwlink/?LinkId=56200) en el sitio Web de Microsoft.  
  
-   **Quitar componentes COM del registro de Windows.** para quitar componentes COM del Registro de Windows, use regsvr32. Para obtener información de referencia, vea "Regsvr32" en la Ayuda del sistema operativo. Esta herramienta se incluye en Windows Server 2008 y Windows Vista Professional.  
  
-   **Desinstalar los ensamblados de la caché de ensamblados global (GAC).** los ensamblados no se desinstalan de forma automática de la GAC. Puede desinstalar un ensamblado de la GAC de forma manual o mediante un script. Para obtener más información, consulte [cómo desinstalar un ensamblado de la GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para quitar los archivos y la configuración descritos en este tema, debe iniciar sesión con los permisos de lectura del Registro de Windows, la GAC o el almacén de certificados, según lo que desee quitar. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)   
 [Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)