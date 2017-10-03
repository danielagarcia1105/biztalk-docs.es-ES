---
title: "Anular la implementación de un adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a8da6ff335460cbd957a33ac5074f65205dfb77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>Anular la implementación de un adaptador mediante el SDK de adaptador LOB de WCF
Para anular la implementación de un adaptador desde un equipo, el usuario debe realizar las dos tareas siguientes:  
  
1.  Desinstalar el ensamblado de adaptador (y cualquier ensamblado dependiente) desde la caché de ensamblados global (GAC).  
  
2.  Quitar el enlace del adaptador y el elemento de enlace de adaptador en el archivo machine.config.  
  
## <a name="uninstall-an-assembly-from-the-gac"></a>Desinstalar un ensamblado de la GAC  
  
#### <a name="use-the-windows-interface"></a>Utilice la interfaz de Windows  
  
1.  Abra el Explorador de Windows como se indica a continuación: haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **elExploradordeWindows**.  
  
2.  Vaya a la GAC, que se encuentra en % systemdrive%\Windows\Assembly.  
  
3.  Haga clic en cada archivo de ensamblado que se incluye en la aplicación, haga clic en **desinstalar**y, a continuación, haga clic en **Sí** para confirmar.  
  
#### <a name="use-the-command-line"></a>Usar la línea de comandos  
  
1.  Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
2.  En el símbolo del sistema, escriba el comando siguiente:  
  
     **Gacutil /u** \< *completo**nombre de ensamblado*>  
  
     En este comando, el nombre del ensamblado es el nombre del ensamblado que se va a desinstalar de la GAC.  
  
     En el ejemplo siguiente se quita el ensamblado denominado hello.dll de la GAC.  
  
     `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a>Quite el enlace del adaptador desde el archivo Machine.config  
 Manualmente, puede editar el archivo machine.config para quitar el enlace del adaptador o usar el Editor de configuración de servicio. Esta sección enumeran los pasos. 
  
#### <a name="manually-edit-the-machineconfig-file"></a>Editar manualmente el archivo machine.config  
  
1.  Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **el Bloc de notas \<ruta de instalación de Windows > \Microsoft.NET\Framework\\< versión\>\CONFIG \Machine.config**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Realizar una copia de seguridad del archivo machine.config antes de realizar cambios para protegerse contra errores de edición.  
  
2.  Actualice el archivo machine.config. Busque el elemento bindingExtensions para el adaptador que desea quitar. Basándose en la otra información que está presente, realice una de las siguientes acciones:  
  
    -   Si hay otros bindingExtensions, quite sólo la extensión del adaptador.  
  
    -   Si no hay ningún otro bindingExtensions, puede quitar la sección bindingExtensions (incluida la extensión de adaptador).  
  
    -   Si no hay ningún otro bindingExtensions o extensiones, puede quitar la sección de extensiones.  
  
    -   Por último, si system.serviceModel contiene solo la extensión de adaptador, puede quitar la sección system.serviceModel todo.  
  
3.  Repita el paso 2 para el elemento bindingElementExtensions.  
  
4.  Cierre y guarde el archivo machine.config.  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a>Use el Editor de configuración de servicio cambia el archivo machine.config  
  
1.  Abra el Editor de configuración de servicio. Vea [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para obtener más información.
  
2.  En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos. Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione el elemento de extensiones de enlace.  
  
3.  En el panel de detalles del Editor de extensiones de enlace, haga clic en la extensión de enlace que desea eliminar y, a continuación, haga clic en **eliminar**. En la ilustración siguiente, MyAdapterExtension se resalta y se eliminará.  
  
     ![Editor de configuración de servicio con extensión agregada. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
4.  Cierre el editor de configuración de servicio.  
  
## <a name="see-also"></a>Vea también  
 [Limitaciones de la implementación](../../core/deployment-limitations1.md)   
 [Implementar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)