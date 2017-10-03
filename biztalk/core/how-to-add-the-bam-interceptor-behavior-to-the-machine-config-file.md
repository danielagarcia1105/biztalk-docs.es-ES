---
title: "Cómo agregar el comportamiento del Interceptor BAM al archivo Machine.config | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8845333389c95ea52d440437935d4c4867dc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a>Cómo agregar el comportamiento del interceptor de BAM al archivo Machine.config.
Para interceptar datos en BAM, debe agregar el comportamiento del interceptor de BAM al archivo machine.config de Microsoft .NET. Hay dos maneras de hacerlo:  
  
-   Editar de forma manual el archivo machine.config para incluir el comportamiento.  
  
-   Usar el editor de configuración de servicio para incluir el comportamiento.  
  
### <a name="to-manually-edit-the-machineconfig-file"></a>Para editar de forma manual el archivo machine.config  
  
1.  Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config y, a continuación, haga clic en **Aceptar**.  
  
2.  Actualice el archivo machine.config con las siguientes extensiones de comportamiento.  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  Cierre y guarde el archivo machine.config.  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a>Para editar el archivo machine.config mediante el uso del editor de configuración de servicio  
  
1.  Abra el editor de configuración de servicio. Para obtener información acerca de cómo utilizar el Editor de configuración de servicio, consulte [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).  
  
2.  En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos. Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione la **las extensiones de elemento de comportamiento** elemento.  
  
3.  Cree una nueva extensión de elemento de comportamiento. Haga clic en el **New** botón para abrir el cuadro de diálogo Editor de elementos de configuración de extensiones. En **nombre de configuración** escriba un nombre único para el comportamiento, por ejemplo, BAMEndPointBehaviorExtension.  
  
     ![Editor de elementos de configuración de extensiones](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")  
  
4.  Haga clic en el **tipo** campo y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el cuadro de diálogo del explorador de tipos de extensión de comportamiento.  
  
5.  Haga clic en el icono de la caché de ensamblados global (GAC) para enumerar las DLL en GAC.  
  
6.  Seleccione el ensamblado Microsoft.BizTalk.Bam.Interceptors.  
  
7.  Haga clic en el **abiertos** botón para seleccionar el ensamblado y, a continuación, cierre el cuadro de diálogo.  
  
     ![Explorador de tipos de extensión Bejavopr](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")  
  
8.  En el panel Nombre de tipo del cuadro de diálogo del explorador del tipo de extensión de comportamiento, haga doble clic en el tipo Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior (resaltado en la siguiente pantalla).  
  
     ![Explorador de tipos de extensión Bejavopr](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")  
  
     Con esto se abre el editor de elementos de configuración de extensiones.  
  
9. Haga clic en **Aceptar** para cerrar el cuadro de diálogo Editor de elementos de configuración de extensiones.  
  
10. En el panel de detalles del editor de configuración de servicio, compruebe que aparece BAMEndPointBehaviorExtension.  
  
11. Cierre el editor de configuración de servicio.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Cómo configurar la intercepción de WCF de BAM](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador WCF para interceptar datos BAM](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)