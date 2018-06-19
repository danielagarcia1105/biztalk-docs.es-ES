---
title: 'Paso 9: Compilar e implementar el adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b9a4985629427e44b8ca85f324c89ab719cf249
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967242"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a>Paso 9: Compilar e implementar el adaptador de eco
![Paso 9 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 **Tiempo en completarse:** 10 minutos  
  
 En este paso, realizará las tareas necesarias para implementar el adaptador de eco. Esto implica que todos los elementos siguientes:  
  
-   Cree un archivo de nombre seguro y asignarlo al ensamblado del adaptador de eco  
  
-   Crear el adaptador de eco  
  
-   Publicar el ensamblado en la GAC  
  
-   Registrar el adaptador de eco con el[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para completar correctamente este paso, debe estar familiarizado con los archivos de nombre seguro y la GAC. Un conocimiento básico de [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuración es útil, pero no es obligatorio.  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>Para asignar un nombre seguro al ensamblado  
  
1.  En el Explorador de soluciones, haga clic en el **EchoAdapter** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades de EchoAdapter, seleccione **firma** en el panel izquierdo.  
  
3.  Haga clic en el **firmar el ensamblado** ficha.  
  
4.  Elija  **\<nuevo... \>**  para el archivo de nombre seguro. Cuando se le solicite un nombre de archivo, escriba **EchoAdapter.snk**, anule la selección de la proteger mi archivo de clave con una opción de contraseña, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en el **aplicación** ficha.  
  
6.  Cambie el nombre de ensamblado a **Microsoft.Adapters.Samples.EchoV2**.  
  
7.  Haga clic en **archivo** en el menú de Visual Studio, a continuación, elija **guardar todo**.  
  
### <a name="to-build-and-deploy-echo-adapter"></a>Para compilar e implementar el adaptador de eco  
  
1.  En el Explorador de soluciones, haga clic en el **EchoAdapter** del proyecto y, a continuación, haga clic en **generar**. Si la compilación no se realiza correctamente, corrija los errores e intente volver a generar el adaptador de eco.  
  
2.  Abra un símbolo del sistema de Visual Studio.  
  
3.  Escriba el siguiente comando:  
  
     **Gacutil.exe /if "\<**  *ruta de acceso a assembly\Microsoft.Adapters.Samples.EchoV2.dll*  **\>"**  
  
     Se instalará el ensamblado en la GAC, sobrescribiendo cualquier ensamblado existente con el mismo nombre.  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a>Para registrar el adaptador de eco con Windows Communication Foundation  
  
1.  Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **el Bloc de notas \<ruta de instalación de Windows\>\Microsoft.NET\Framework\\< versión\>\CONFIG\machine.config**y, a continuación, haga clic en **Aceptar**.  
  
2.  Actualice el archivo machine.config. Si el archivo machine.config no contiene una sección de system.serviceModel, agregue la siguiente sección al final del archivo de configuración, pero antes de que el cierre raíz etiqueta.  
  
    > [!NOTE]
    >  Reemplace la versión, referencia cultural, token de clave pública y otra información específica del ensamblado con la información de su adaptador.  
  
    ```  
    <system.serviceModel>  
      <client>  
        <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
          name="echov2" />  
      </client>  
      <extensions>  
        <bindingElementExtensions>  
          <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingElementExtensions>  
        <bindingExtensions>  
          <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
     - O BIEN  
  
     Si el archivo machine.config contiene una sección de system.serviceModel, determinar qué elementos se encuentran y agregan.  
  
    > [!NOTE]
    >  Reemplace la versión, referencia cultural, token de clave pública y otra información específica del ensamblado con la información de su adaptador.  
  
    ```  
    <client>  
      <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
        name="echov2" />  
    </client>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingElementExtensions>  
      <bindingExtensions>  
        <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingExtensions>  
    </extensions>  
    ```  
  
3.  Guarde el archivo machine.config.  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso final del tutorial de adaptador de eco, agrega un nombre seguro para el adaptador de eco, compilado e implementa el adaptador y modifica Machine.config para incluir información acerca del adaptador. En este momento, el adaptador de eco debería estar disponible para consumir las aplicaciones.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Este tutorial está completado. Si desea probar la funcionalidad del adaptador de eco en un proyecto. NET, consulte [Tutorial 2: utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 8: Implementar el controlador de entrada sincrónico para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)   
 [Tutorial 2: Usar el adaptador de Echo desde .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)