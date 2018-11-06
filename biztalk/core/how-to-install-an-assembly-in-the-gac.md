---
title: Cómo instalar un ensamblado en la GAC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6afc2f81-fa28-4144-b4bd-21c8f35f2270
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e843d74b5420f8973f9d3663cfd05210c26996
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752369"
---
# <a name="how-to-install-an-assembly-in-the-gac"></a>Cómo instalar un ensamblado en la GAC
Instalar y desinstalar un ensamblado de BizTalk en la memoria caché global de ensamblados (GAC) mediante la herramienta Gacutil incluida con manualmente [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
 Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], puede hacer que los ensamblados de BizTalk se instala automáticamente en la GAC cuando se implementan desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Establezca esta opción en las propiedades de implementación del proyecto de BizTalk; consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). No puede utilizar este método para instalar los ensamblados de .NET que no sean de BizTalk en la GAC; debe instalarlos manualmente, tal como se describe en este tema.  
  
> [!NOTE]
>  También se pueden especificar opciones de implementación para ensamblados una vez implementados en una aplicación de BizTalk mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Consulte [cómo modificar las opciones de implementación de un ensamblado de BizTalk](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md), y [cómo modificar las opciones de implementación de un ensamblado .NET, un componente COM, un archivo o un artefacto de BAM](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que tenga permiso de escritura en la GAC. La cuenta de administradores del equipo local cuenta con este permiso.  

  
## <a name="install-using-gacutil"></a>Instalación mediante gacutil
  
1.  Copie el ensamblado de BizTalk en el equipo local.  
  
2.  Abra **símbolo del sistema para desarrolladores de Visual Studio** como administrador.  
  
3.  Escriba lo siguiente:  
  
     `gacutil /i path_to_assembly_file /f`

    Por ejemplo, escriba:  
    `gacutil /i c:\temp\filename.dll /f`
    
El `/f` opción sobrescribe cualquier ensamblado existente que tiene el mismo nombre de ensamblado. Para obtener más información sobre los comandos gacutil y opciones, escriba `gacutil /?`. 

## <a name="uninstall-using-gacutil"></a>Desinstalar mediante gacutil
Desinstalar un ensamblado de la caché global de ensamblados (GAC) es necesario anular totalmente la implementación de una aplicación. Puede automatizar este proceso. Antes de implementar la aplicación en un entorno de producción, escribir una secuencia de comandos previa al procesamiento que desinstala el ensamblado de la GAC automáticamente cuando se desinstala la aplicación. Consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicación](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).  
  
 También puede usar un script para quitar archivos adicionales y opciones. Consulte [cómo quitar otros archivos y configuraciones para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
 
#### <a name="using-the-windows-interface"></a>Utilización de la interfaz de Windows  
  
1.  Abrir en % systemdrive%\Windows\Assembly.  
  
2.  Haga clic en cada archivo de ensamblado incluido en la aplicación, seleccione **desinstalar**y, a continuación, seleccione **Sí** para confirmar.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra **símbolo del sistema para desarrolladores de Visual Studio** como administrador. 
  
2.  Escriba lo siguiente:  
  
     `gacutil /u` \<*nombre completo del ensamblado*\>  
  
     Por ejemplo, escriba:  
     `gacutil /u "hello,Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"`
       
## <a name="see-also"></a>Vea también  
 [Implementación de ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
[Anular la implementación de aplicaciones de BizTalk](../core/undeploying-biztalk-applications.md)   
 [Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)   
 [Cómo eliminar una aplicación de BizTalk del grupo de BizTalk](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)
 
