---
title: Solucionar problemas de instalación con el adaptador de Siebel | Microsoft Docs
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
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed3fab4973950b70a49efc90e1bc947561e602c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983501"
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a>Solucionar problemas de instalación con el adaptador de Siebel
Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador. En esta sección se describe las técnicas de solución de problemas para resolver errores de instalación.  

## <a name="setup-logging"></a>Configuración del registro  
 El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Además, el programa de instalación también lleva a cabo determinadas acciones como el registro de los enlaces del adaptador personalizados. Puede registrar mensajes para las acciones de estándares como personalizadas realizadas por el programa de instalación.  

- El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación instala los archivos específicos del adaptador mediante MSI. Por lo tanto, el registro para el programa de instalación será el registro de MSI estándar.  

- Los registros para las acciones personalizadas realizadas por el programa de instalación están disponibles en % TEMP%\adaptersetup.log. Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.  

## <a name="known-issues"></a>Problemas conocidos  

### <a name="setup-fails-to-register-adapter-bindings"></a>Se produce un error en el programa de instalación registrar los enlaces del adaptador  
 **Problema**  

 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] produce un error en el Asistente para la instalación registrar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace o el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], pero continúa con la instalación del adaptador.  

 **Causa**  

 Esto podría producir debido a problemas con la instalación de WCF, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados. Los enlaces del adaptador se escriben en el archivo machine.config.  

 **Resolución**  

Registrar manualmente el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace y [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] siguiendo estos pasos: 

1. Navegue al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  

    En esta ruta de acceso, \<versión\> es la versión de .NET Framework.  

2. Abra el archivo con un editor de texto.  

3. Para registrar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace:  

   1. Busque el elemento "system.serviceModel" y agregue lo siguiente en él:  

      ```  
      <client>  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
      </client>  
      ```  

   2. Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.  

   3. Busque el campo que falta [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace. Agregue la siguiente sección en el nodo "bindingElementExtensions".  

       Para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], agregue:  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.  

   5. Busque el campo que falta [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace. Agregue las siguientes secciones en el nodo "bindingExtensions".  

       Para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], agregue:  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

      > [!NOTE]
      >  Para obtener información sobre cómo determinar la clave pública, consulte [determinar la clave pública y la versión](#BKMK_PubKey).  

4. Para registrar el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:  

   1. Busque el elemento DbProviderFactories bajo el nodo system.data.  

   2. Busque el campo que falta [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]. Agregue la siguiente sección en el nodo DbProviderFactories.  

       Para [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], agregue:  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. Guarde y cierre el archivo machine.config.  

####  <a name="BKMK_PubKey"></a> Determinación de la clave pública y versión  
 Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] o [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].  

###### <a name="to-determine-the-public-key"></a>Para determinar la clave pública  

1. Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.  

2. Haga clic en el archivo DLL para el que desea que el público clave y seleccione **propiedades**. En la tabla siguiente se muestra el nombre de los archivos DLL para cada adaptador y el proveedor.  


   |                              Proveedor de ADO/adaptador                               |       Nombre del archivo DLL       |
   |---------------------------------------------------------------------------------|-----------------------------|
   |    [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]    |  Microsoft.Adapters.Siebel  |
   | [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] | Microsoft.Data.SiebelClient |


3. En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL. De forma similar, valor frente a la **versión** etiqueta Especifica el número de versión para el archivo DLL.  

4. Copie la clave pública y, a continuación, haga clic en **cancelar**.  

## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)