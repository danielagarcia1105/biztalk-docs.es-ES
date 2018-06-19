---
title: Solucionar problemas de instalación con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc33d5d15ef876e18a5a17fa33944dd7d1b36461
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964154"
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a>Solucionar problemas de instalación con el adaptador SAP
Instalación del software Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador. Esta sección describen técnicas de solución de problemas para resolver errores de instalación.  
  
## <a name="logging-messages-for-setup-actions"></a>Mensajes de registro de acciones de instalación  
 El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Además, el programa de instalación también realiza algunas acciones personalizadas como el registro de los enlaces del adaptador. Puede registrar mensajes para las acciones estándares, así como personalizadas que realiza el programa de instalación.  
  
-   El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación instala los archivos específicos del adaptador con un archivo MSI. Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.  
  
-   Registros para las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log. Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.  
  
##  <a name="BKMK_SAPSetupBinding"></a>El programa de instalación no puede registrar los enlaces del adaptador o proveedores de datos  
 **Problema**  
  
 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar los enlaces del adaptador o [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], pero continúa con la instalación del adaptador.  
  
 **Causa**  
  
 Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config está dañado. Los enlaces del adaptador se escriben en el archivo machine.config.  
  
 **Resolución**  
  
 Debe registrar manualmente el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace o [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
### <a name="register-the-adapter-bindings-or-the-data-provider"></a>Registrar los enlaces del adaptador o el proveedor de datos  
  
1.  Navegue hasta el archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidad del sistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  
  
     En esta ruta de acceso, \<versión\> es la versión de .NET Framework.  
  
2.  Abra el archivo con un editor de texto.  
  
3.  Para registrar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace:  
  
    1.  Busque el elemento "system.serviceModel" y agregue lo siguiente en él:  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        </client>  
        ```  
  
    2.  Busque el elemento "bindingElementExtensions" en system.serviceModel\extensions.  
  
    3.  Busque la falta [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace. Agregue la siguiente sección bajo el nodo "bindingElementExtensions".  
  
         Para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], agregue:  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  Busque el elemento "bindingExtensions" en system.serviceModel\extensions.  
  
    5.  Busque la falta [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace. Agregue la siguiente sección bajo el nodo "bindingExtensions".  
  
         Para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], agregue:  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).  
  
4.  Para registrar el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
    1.  Busque el elemento "DbProviderFactories" bajo el nodo "system.data".  
  
    2.  Busque la falta [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]. Agregue la siguiente sección bajo el nodo "DbProviderFactories".  
  
         Para [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], agregue:  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  Guarde y cierre el archivo machine.config.  
  
###  <a name="BKMK_PubKey"></a>Determinar la versión y la clave pública  
 Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] o [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
1.  Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.  
  
2.  Haga clic en el archivo DLL para el que desea que la clave pública y, a continuación, seleccione **propiedades**. En la tabla siguiente muestra el nombre de los archivos DLL para [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
    |Proveedor de datos del adaptador|Nombre de la DLL|  
    |----------------------------|---------------------|  
    |[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
  
3.  En el **General** pestaña, el valor en el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL. Valor de forma similar, en la **versión** etiqueta Especifica el número de versión para el archivo DLL.  
  
4.  Copie la clave pública y, a continuación, haga clic en **cancelar**.  
  
##  <a name="BKMK_SAPConsumeBinding"></a>Ningún adaptador válidos es error instalados

 **Problema**  
  
 Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:  
  
```  
No valid adapters are installed on this machine  
```  
  
 **Causa**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config. Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits. Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config. Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando se inicia el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], el complemento comprueba los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.  
  
 **Resolución**  
  
-   Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.  
  
    > [!IMPORTANT]
    >  Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.  
  
-   Agregue las versiones de 32 bits y 64 bits de los archivos DLL de cliente para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (por ejemplo, librfc32u.dll) a la variable PATH. La versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64. La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
  
    > [!IMPORTANT]
    >  Si se ejecuta el adaptador (32 o 64 bits) en un equipo que tenga un sistema operativo de 64 bits y que usa el adaptador para escribir una aplicación, debe marcar la aplicación en el mismo tipo que el adaptador (32 o 64 bits). Además, la versión de RFC SDK (32 o 64 bits) debe ser igual que la versión del adaptador (32 o 64 bits).  
    >   
    >  Por ejemplo, si un adaptador de 32 bits se ejecuta en un equipo con un sistema operativo de 64 bits, la aplicación de cliente de adaptador debe marcarse como de 32 bits.  
  
     Para obtener más información acerca del cliente SAP archivos DLL, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).  
  
##  <a name="BKMK_SAPInvalidBinding"></a>Error de enlace no válido al configurar los puertos de adaptador SAP  
 **Problema**  
  
 Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 **Causa**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config. Una plataforma de 64 bits tiene dos machine.config (archivos), uno utilizados por las aplicaciones de 32 bits y el otro utilizados por las aplicaciones de 64 bits. Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config. Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración se ejecuta como un proceso de 32 bits y, por tanto, cuando configura un puerto para el adaptador, comprueba si los enlaces en la versión de 32 bits del archivo machine.config y no se puede dar un error.  
  
 **Resolución**  
  
-   Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.  
  
    > [!IMPORTANT]
    >  Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.  
  
-   Agregue las versiones de 32 bits y 64 bits de los archivos DLL de cliente para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (por ejemplo, librfc32u.dll) a la variable PATH. La versión de 32 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\SysWow64. La versión de 64 bits de los archivos DLL debe agregarse a la carpeta C:\Windows\System32.  
  
    > [!IMPORTANT]
    >  Si se ejecuta el adaptador (32 o 64 bits) en un equipo que tenga un sistema operativo de 64 bits y que usa el adaptador para escribir una aplicación, debe marcar la aplicación en el mismo tipo que el adaptador (32 o 64 bits). Además, la versión de RFC SDK (32 o 64 bits) debe ser igual que la versión del adaptador (32 o 64 bits).  
    >   
    >  Por ejemplo, si un adaptador de 32 bits se ejecuta en un equipo con un sistema operativo de 64 bits, la aplicación de cliente de adaptador debe marcarse como de 32 bits.  
  
     Para obtener más información acerca del cliente SAP archivos DLL, consulte [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)