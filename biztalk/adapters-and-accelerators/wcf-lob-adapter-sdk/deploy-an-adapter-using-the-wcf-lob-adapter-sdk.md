---
title: Implementar un adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11ae1067fff276d8d24639d3e4d3cc6798c6ba5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>Implementar un adaptador mediante el SDK de adaptador LOB de WCF
Para implementar un adaptador, debe instalar al ensamblado de adaptador en la caché global de ensamblados (GAC) y, a continuación, registrar el adaptador en el archivo machine.config.  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a>Instalar al ensamblado de adaptador en la GAC  
 Antes de consumir un adaptador en Visual Studio mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] comandos o en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] utilizando el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] característica, debe instalar el ensamblado en la GAC. Solo los ensamblados con nombre seguro pueden instalarse en la GAC.  
  
> [!NOTE]
>  Para completar este procedimiento, debe ser iniciado sesión con una cuenta que tenga permisos de escritura en la GAC. La cuenta de administradores del equipo local tiene estos permisos.  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a>Configurar un archivo de clave de ensamblado de nombre seguro  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], cargue el archivo de proyecto de adaptador que necesita un nombre seguro.  
  
2.  Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
3.  En el símbolo del sistema, desde la carpeta donde desea almacenar el archivo de clave, escriba el comando siguiente y, a continuación, presione ENTRAR:  
  
     **sn /k***file_name* **.snk**   
  
     Ejemplo: **sn /k EchoAdapter.snk**  
  
     Un mensaje de confirmación, **escribe en el par de claves** \< *file_name*\>**.snk** `,` muestra en la línea de comandos.  
  
4.  En el Explorador de soluciones de Visual Studio, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.  
  
5.  En el panel izquierdo, expanda **propiedades comunes**y, a continuación, haga clic en **ensamblado**.  
  
6.  En el panel derecho, desplácese a la **nombre seguro** cuadro.  
  
7.  En el **nombre seguro** cuadro, haga clic en el campo junto a **archivo de clave de ensamblado**, haga clic en el botón Examinar (**...** ) y, a continuación, busque el archivo de clave.  
  
8.  Haga clic en el archivo de clave, haga clic en **abiertos**y, a continuación, haga clic en **Aceptar**.  
  
9. En el menú de Visual Studio, haga clic en **generar**y, a continuación, elija **generar solución**.  
  
> [!NOTE]
>  Si su ensamblado de adaptador depende de otros ensamblados, asegúrese de que estos ensamblados se firman con un nombre seguro; en caso contrario, obtendrá un error.  
  
 Si tiene el código fuente, puede volver a compilar con un nombre seguro tal y como se ha mostrado anteriormente. Si el ensamblado de referencia pertenece a un tercero y no puede garantizar que se le asignará un nombre seguro, puede desensamblar y, a continuación, volver a ensamblar el ensamblado con un nombre seguro.  
  
 El ensamblado original se sobrescribirá, por lo que si desea conservar la versión original, asegúrese de realizar una copia de seguridad del mismo antes de continuar con los pasos siguientes.  
  
 Utilizar el Desensamblador de lenguaje intermedio de Microsoft (MSIL) para desensamblar el ensamblado:  
  
-   ILDASM thirdparty.dll /out:thirdparty.il  
  
 Usar el ensamblador de MSIL para volver a ensamblar el ensamblado con un nombre seguro:  
  
-   ILASM thirdparty.il /dll /key=strongkeyfile.snk  
  
#### <a name="install-an-assembly-in-the-gac"></a>Instalar a un ensamblado en la GAC  
  
1.  Compruebe que el adaptador se ha suscrito.  
  
2.  Abra un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
3.  Escriba el siguiente comando:  
  
     **Gacutil.exe /if "\<**  *ruta de acceso al archivo .dll del ensamblado*  **\>"**  
  
4.  Se instalará el ensamblado en la GAC, sobrescribiendo cualquier ensamblado existente con el mismo nombre.  
  
## <a name="register-the-adapter-in-machineconfig"></a>Registrar el adaptador en el archivo Machine.config  
 Un adaptador desarrolladas con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparece como un enlace de WCF.  Para obtener más información, consulte Microsoft.ServiceModel.Channels.Common.AdapterBinding.  El enlace del adaptador está registrado con WCF con \<bindingExtensions\> sección dentro de \<sistema. ServiceModel\> y el elemento de enlace de transporte de adaptador está registrado con WCF con \<bindingElementExtensions\> sección dentro de \<sistema. ServiceModel\>.  
  
 Puede editar manualmente el archivo machine.config con un editor de texto.  
  
#### <a name="manually-edit-the-machineconfig-file"></a>Editar manualmente el archivo machine.config  
  
1.  Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad \<ruta de instalación de Windows\>\Microsoft.NET\Framework\\< versión\>\CONFIG\ Machine.config y, a continuación, haga clic en **Aceptar**.  
  
2.  Actualice el archivo machine.config. Si el archivo no contiene una sección de system.serviceModel, agregue la siguiente sección al final del archivo de configuración, pero antes de que el cierre raíz etiqueta.  
  
    > [!NOTE]
    >  Reemplace "myAdapterBinding", versión, referencia cultural y otra información específica del ensamblado con la información de su adaptador.  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
        </bindingExtensions>      <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
     - O BIEN  
  
     Si el archivo machine.config contiene una sección de system.serviceModel, determinar qué elementos se encuentran y agregan, reemplazando "MyAdapter" y otra información con la información de su adaptador.  
  
    ```  
    <extensions>  
      <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
      </bindingExtensions>  
          <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
    </extensions>  
    ```  
  
3.  Cierre y guarde el archivo machine.config.  
  
 También puede usar el [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para modificar el archivo machine.config.
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a>Edite el archivo machine.config con el Editor de configuración de servicio  
  
1.  Abra la **Editor de configuración de servicio**. Vea [Editor de configuración de servicio](https://msdn.microsoft.com/library/ms732009.aspx) para obtener más información.
  
2.  En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos. Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione el elemento de extensiones de enlace.  
  
     ![Editor de configuración de servicio. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")  
  
3.  Cree una nueva extensión de enlace. Haga clic en el **New** botón para abrir la extensión **Editor de elementos de configuración** cuadro de diálogo. En **nombre de configuración**, escriba un nombre único para las extensiones, por ejemplo *MyAdapterExtension*.  
  
     ![Editor de elementos de configuración de extensiones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")  
  
4.  Haga clic en el **tipo** campo y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el **Explorador de tipos de extensión de enlace** cuadro de diálogo.  
  
5.  Haga clic en el icono de (GAC) de la caché global de ensamblados para obtener una lista de los archivos DLL en la GAC.  
  
6.  Haga clic en su ensamblado de adaptador.  
  
     ![Crear Explorador de tipo de extensión. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")  
  
7.  Haga clic en el **abiertos** para seleccionar el ensamblado.  
  
8.  En el **el Explorador de tipos de extensión de enlace** diálogo cuadro, haga clic en el nombre del tipo que implementa el elemento de la colección de enlace.  
  
     ![Crear Explorador de tipo de extensión. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")  
  
9. Haga clic en el **abiertos** para seleccionar el tipo.  
  
10. Haga clic en **Aceptar** para cerrar el **Editor de elementos de configuración de extensiones** cuadro de diálogo.  
  
11. En el panel de detalles de la **enlace extensiones de Editor**, compruebe que aparece la extensión de enlace. En la ilustración siguiente, se resalta MyAdapterExtension.  
  
     ![Editor de configuración de servicio con extensión agregada. ] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
12. Cerrar la **Editor de configuración de servicio**.  
  
## <a name="see-also"></a>Vea también  
 [Implementar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)